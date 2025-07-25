# resume.ai
This is the repository that will create to Resume analysis with the help of Generative AI
import streamlit as st 
import google.generativeai as genai
import os
from dotenv import load_dotenv
load_dotenv() # activate the api key
genai.configure(api_key = os.getenv("GEMINI_API_KEY"))

# Movie Recommendation System Front End
st.title("🍿🎥✮⋆˙Movie Recommender System!!🍿🎥✮⋆˙")
user_input = st.text_input("Enter the Movie Name")
submit = st.button("click here..")

model = genai.GenerativeModel("gemini-1.5-flash-002")

if submit:
    response =  model.generate_content(f"Generate Movie Recommendations for {user_input}")
    st.write(f"Recommendations:\n{response.text}")
else:
    st.write(" ")
