import pandas as pd  
from matplotlib.colors import Normalize, rgb2hex
import matplotlib.cm as cm

wrecks = pd.read_csv('http://www.cs.wm.edu/~rml/teaching/csci141/data/AWOIS_Wrecks.csv', encoding='cp1252')

import folium
wmap = folium.Map(location=[37, -76], zoom_start=17)
wmap.save('wmap.html')


for i in wrecks.iterrows():
    lat = wrecks['LATDEC']
    lon = wrecks['LONDEC']

folium.Marker(i[1]['LATDEC'], i[1]['LONDEC'], 
                        popup=f"{i[1]['VESSLTERMS','FEATURE_TYPE']}").add_to(eq_map)
