# for camera testing and working 

import cv2
from PIL import Image
import pytesseract
from colorama import Fore, Style, init

camera = cv2.VideoCapture(1)

if not camera.isOpened():
    print("Camera is not opened")
else:
    print("Camera is opened")

    ret, frame = camera.read()
    if ret: 
        cv2.imwrite("image_packaged_item.jpg", frame)
        print("Image captured successfully",)
    else:
        print("failed to read the frame")

camera.release()

""" now this for extracting the text form the captured image"""
pic = Image.open("image_packaged_item.jpg")
extracted_txt = pytesseract.image_to_string(pic)
print("\n Extracted Text \n", extracted_txt)

""" this is to find the food ingredients in the extracted text """
ingred = extracted_txt.split("\n")
ingredients_use = ""

for line in ingred:
    if "ingredients" in line.lower():
        ingredients_use = line.strip()
        break 
    print(f"{Fore.CYAN}---is there any Ingredient Found---", extracted_txt)
    if ingredients_use:
        print(f"{Fore.CYAN}---Ingredients List---", ingredients_use)
    else:
        print(f"{Fore.RED}---No Ingredients Found---")

# analizing the ingredients are the harmful or not
ingredients_use = extracted_txt
if ":" in ingredients_use:
    ingredients_txt = ingredients_use.split(":")[1].strip()
else:
    ingredients_txt = ingredients_use

ingredients_line = ingredients_txt.split(',')
ingredients_line = ingredients_txt.split(',')

harmfull_ingredients = ["sugar", "maida", "preservatives", "artificial colors", "artificial flavors","palm oil"]
healthy_ingredients = ["Fiber", "Protein", "Vitamin", "Whole grain", "Calcium","Carbohydrate"]

harmfull_coun = 0
healthy_count = 0

for items in ingredients_line:
   if cleaned in harmful_ingredients:
        print(f"{cleaned} Harmful")
        harmful_count += 1
    elif cleaned in healthy_ingredients:
        print(f"{cleaned} Healthy")
        healthy_count += 1
    else:
        print(f"{cleaned} Unknown")

