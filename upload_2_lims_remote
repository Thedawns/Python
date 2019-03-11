import requests, base64
import json, os
import argparse

url="http://180.167.55.206:8788/IGeneExternalInterface/UpLoadResultFile"
def upload_single(file_path,code):
	name = os.path.basename(file_path)
	f = open(file_path, "rb")
	ls_f = base64.b64encode(f.read())
	f.close()
	par = {"LibraryCode":code, "FileName":name,"FileContent": ls_f}
	headers = {'Content-type': 'application/json'}
	r=requests.post(url,data=json.dumps(par),allow_redirects=True,headers=headers)
	print(r.content)


parser = argparse.ArgumentParser(description="file")

parser.add_argument("-d", "--dir", help="file_path", required=True)

parser.add_argument("-c", "--code", help="library_code", required=True)
args = vars(parser.parse_args())

directory = args["dir"]
code = args["code"]
f_lst = [os.path.join(directory,f) for f in os.listdir(directory)]
for f in f_lst:
	upload_single(f, code)
