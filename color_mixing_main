
import colorsys
from colormix_values import *
                    

#### Functions to convert color systems between CMY, RGB, HSV.

def hue_to_cmy(hue_value):
    """Convert a hue value (0 to 255) into CMY."""
    # Red-Yellow range. M100 = red. M0 = Yelow.
    if hue_value in range(0, 60):
        c = 0
        m = int((60 - hue_value) / 60 * 100)
        y = 100
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    # Yellow-Green range. C0 = Yellow. C=100 = green.
    elif hue_value in range(60, 120):
        hue_value = hue_value - 60
        c = int(hue_value / 60 * 100)
        m = 0
        y = 100
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    # Green-Cyan range. Y100 = Green. Y0 = Cyan.
    elif hue_value in range(120, 180):
        c = 100
        m = 0
        y = int((180 - hue_value) / 60 * 100)
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    # Cyan-Blue range. M0 = Cyan. M100 = Blue.
    elif hue_value in range(180, 240):
        hue_value = hue_value - 180
        c = 100
        m = int(hue_value / 60 * 100)
        y = 0
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    #Blue-Magenta range. C100 = Blue. C0 = Magenta.
    elif hue_value in range(240, 300):
        c = int((300 - hue_value) / 60 * 100)
        m = 100
        y = 0
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    #Magenta-Red range. Y0 = Magenta. Y100 = Red.
    elif hue_value in range(300, 361):
        hue_value = hue_value - 300
        c = 0
        m = 100
        y = int(hue_value / 60 * 100)
        print("C: " + str(c) + " M: " + str(m) + " Y: " + str(y))
    else:
        pass
    return [c, m, y]
    

def cmy_to_hue(cmy):
    """Convert CMY values into RGB, then convert RGB to HSL, then convert HSL to Hue # between 0-360."""
    # 100% minus Cyan's %. 
    # Multiply by 0.01 to find 'percentage fraction'
    # Multiply this 'opposite percentage' of Cyan by 255 to find RGB's value.
    # Divide the ###/255 value by 255 to find decimal value (0-1).
    # Convert to HLS with colorsys function.
    # Convert HLS's hue value from decimal value (0-1) to hue value (0-360)
    r = (255 * ((100 - cmy[0]) * 0.01)) / 255
    g = (255 * ((100 - cmy[1]) * 0.01)) / 255
    b = (255 * ((100 - cmy[2]) * 0.01)) / 255
    hls = colorsys.rgb_to_hls(r, g, b)
    h = int(hls[0] * 360)
    return h


#### Testing with 'Vermillion' and 'Cobalt' from the color table I made. 
#lightish_muted_vermillion
vermillion = colors[100]
#neutral_intense_cobalt 
cobalt = colors[850]

# Show each color's original Hue Value, pulled from their dictionary from my auto-generated color table.
print(vermillion['name'] + ' HSL Hue Value: ' + str(vermillion['hue']))
print(cobalt['name'] + ' HSL Hue Value: ' + str(cobalt['hue']))

# Convert the Vermillion and Cobalt from hue values in the HSL 0-360 format into CMY values.
verm_cmy = hue_to_cmy(vermillion['hue'])
cob_cmy = hue_to_cmy(vermillion['hue'])
print("\nLightish Muted Vermillion CMY Values: " + str(verm_cmy))
print("Neutral Intense Cobalt CMY Values: " + str(cob_cmy))

# Convert the Vermillion and Cobalt back to HSL's Hue Value between 0-360.
verm_hue = cmy_to_hue(verm_cmy)
cob_hue = cmy_to_hue(cob_cmy)
print(f"\nVermillion HLS Hue Value: {verm_hue}")
print(f"Cobalt HLS Hue Value: {cob_hue}")

            
            
            
            
            
    
