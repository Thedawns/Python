class adjust(object):
	
	def __init__(self,infile):
		import PIL
		from PIL import Image
		self.infile = self
		prefix = infile[0:-4]
		outfile = "%s_adjust.jpg" % prefix
		im = Image.open(infile)
		(x, y) = im.size
		x_s = 600
		y_s = 600
		out = im.resize((x_s, y_s), Image.ANTIALIAS)
		out.save(outfile)
