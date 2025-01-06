import streamlit as st
import pandas as pd

# Title
st.title("CSV File Data Explorer")

# Sidebar for uploading CSV file
st.sidebar.header("Upload CSV File")
uploaded_file = st.sidebar.file_uploader("Upload a CSV file", type=["csv"])

if uploaded_file:
    # Load the uploaded CSV file into a DataFrame
    data = pd.read_csv(uploaded_file)

    # Display dataset preview
    st.header("Dataset Preview")
    st.write(data.head())

    # Display basic dataset info
    st.subheader("Basic Information")
    buffer = []
    data.info(buf=buffer)
    st.text("".join(buffer))

    # Display dataset statistics
    st.subheader("Descriptive Statistics")
    st.write(data.describe())

    # Show dataset columns
    st.subheader("Dataset Columns")
    st.write(data.columns.tolist())

    # Option to visualize missing values
    if st.checkbox("Show Missing Values Summary"):
        st.write(data.isnull().sum())

else:
    st.info("Please upload a CSV file to get started.")
