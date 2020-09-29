conversiondict = {'Ala': 'A',
                  'Asx': 'B',
                  'Cys': 'C',
                  'Asp': 'D',
                  'Glu': 'E',
                  'Phe': 'F',
                  'Gly': 'G',
                  'His': 'H',
                  'Ile': 'I',
                  'Lys': 'K',
                  'Leu': 'L',
                  'Met': 'M',
                  'Asn': 'N',
                  'Pro': 'P',
                  'Gln': 'Q',
                  'Arg': 'R',
                  'Ser': 'S',
                  'Thr': 'T',
                  'Val': 'V',
                  'Trp': 'W',
                  'Tyr': 'Y',
                  'Glx': 'Z'
                  }
conversionlist = conversiondict.keys()
def conversion(hgvs):
    threecharactersearch = re.findall('[a-zA-Z]{3}\d+', hgvs, flags=re.IGNORECASE)
    if threecharactersearch:
        if any(letters.lower() in hgvs.lower() for letters in conversionlist):
            return replace_all(hgvs)
    return hgvs

def replace_all(hgvs):
    # Author: Thomas Glaessle
    pattern = re.compile('|'.join(conversionlist), re.IGNORECASE)
    return pattern.sub(lambda m: conversiondict[m.group().capitalize()], hgvs)
