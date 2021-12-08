import streamlit as st
import numpy as np
import pandas as pd
import sklearn
from PIL import Image, ImageTk
import numpy as np

import random

from os import walk
st.markdown("# This is Magic Card Game!")
st.text("Suppose a number between 1 to 127")
#start = st.button("Let's Start")

filenames = next(walk(r"E:\magic card"), (None, None, []))[2]  # [] if no file

card_permutation = list(np.random.permutation(7))
for i in range(len(card_permutation)):
    card_permutation[i] += 1
st.sidebar.text("Choose card numbers that your\nsupposed number exists in it")
b1 = st.sidebar.checkbox("card number 1", key="1")
b2 = st.sidebar.checkbox("card number 2", key="2")
b3 = st.sidebar.checkbox("card number 3", key="3")
b4 = st.sidebar.checkbox("card number 4", key="4")
b5 = st.sidebar.checkbox("card number 5", key="5")
b6 = st.sidebar.checkbox("card number 6", key="6")
b7 = st.sidebar.checkbox("card number 7", key="7")
b=[b1,b2,b3,b4,b5,b6,b7]


def Magic_Card():

    for number in range(1,8):
        #im = Image.open(filenames[number - 1])
        im = Image.open(fr"E:\magic card\{number}.jpg")
        st.image(im, width=300)
        st.write(f"card number {i+1}")



logo = Image.open(r"E:\Hellomath\logo high quality 1080 hh Png.png")
st.image(logo, width=200)

Magic_Card()
a = 0
finish = st.sidebar.button("Finish")
for i,btn in enumerate(b):
    if btn:
        a += 2 ** (i)

if finish:
    st.sidebar.write(a)
    st.slider.success("Success")
