# Downloading-data-from-webpage-using-Python #
import urllib2
import urllib

csv_url = 'https://query1.finance.yahoo.com/v7/finance/download/GOOG?period1=1500303159&period2=1502981559&interval=1d&events=history&crumb=pCcgdrgWYwJ'

# main function which downloads the data #

def download_csvfile(url):
    response = urllib.urlopen(url)
    csv = response.read()
    csv_str = str(csv)
    lines = csv_str.split("\\n")
    dest_url = r'google.csv'
    fx = open(dest_url,'w')
    for line in lines:
        fx.write(line,'\\n')
    fx.close()

download_csvfile(csv_url)
