# Streamlit Guide
*A Production-Ready Documentation Blueprint*

# 📦 1. Installation & Project Setup

## Install Dependencies
```bash
pip install streamlit pandas
```

## Project Structure (Recommended)
This strucutre is for following this guide. You can modify it as needed for your project.
```
streamlit-dashboard/
│
├── app.py
├── tiger.webp
├── requirements.txt
└── pages/
    ├── 1_Dashboard.py
    └── 2_Settings.py
```

## Run Application

```bash
streamlit run app.py
```


# 2. Page Configuration

Always define configuration at the top of the script:

```python
import streamlit as st

st.set_page_config(
    page_title="Startup Dashboard",
    page_icon="🚀",
    layout="wide",
    initial_sidebar_state="expanded"
)
```

# 3. Understanding Streamlit’s Core Concept

## Rerun Behavior

> Streamlit reruns the entire script every time a widget value changes.  
This is the most important concept in Streamlit.

Because of this:
* Variables reset
* Data reloads
* UI refreshes

To solve this → use **Session State**.

# 🔐 4. Session State (State Management)

Used to persist values across reruns.

```python
if "count" not in st.session_state:
    st.session_state.count = 0

if st.button("Increase"):
    st.session_state.count += 1

st.write("Count:", st.session_state.count)
```

### When to Use
* Login systems
* Multi-step forms
* Counters
* Storing uploaded data
* Page navigation

# 5. Text & Content Display

## Titles & Headers

```python
st.title("Startup Dashboard")
st.header("Analytics Overview")
st.subheader("Monthly Performance")
```

## Markdown

```python
st.markdown("""
### Features
- Real-time analytics
- File uploads
- Interactive charts
""")
```

## Code Display

```python
st.code("print('Hello Streamlit')", language="python")
```

## LaTeX

```python
st.latex("x^2 + y^2 = z^2")
```


# 6. Data Display & Metrics

## DataFrame

```python
import pandas as pd

df = pd.DataFrame({
    "Name": ["Ruhul", "Karim"],
    "Marks": [50, 60]
})

st.dataframe(df)
```

## Metrics

```python
st.metric("Revenue", "BDT 3L", "+3%")
```

## JSON

```python
st.json(df.to_dict())
```


# 7. Charts & Data Visualization

## Built-in Charts

```python
st.line_chart(df["Marks"])
st.bar_chart(df["Marks"])
st.area_chart(df["Marks"])
```

## Using Matplotlib

```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots()
ax.plot(df["Marks"])
st.pyplot(fig)
```

## Using Plotly (Advanced)

```python
import plotly.express as px

fig = px.bar(df, x="Name", y="Marks")
st.plotly_chart(fig)
```


# 8. Media Rendering

```python
st.image("tiger.webp", caption="Bengal Tiger")
st.video("https://www.youtube.com/watch?v=gA-4fA_7kc8")
st.audio("audio.mp3")
```


# 9. Layout System

## Sidebar

```python
st.sidebar.title("Navigation")
```

## Columns

```python
col1, col2 = st.columns([2, 1])

with col1:
    st.write("Main content")

with col2:
    st.write("Side content")
```

## Tabs

```python
tab1, tab2 = st.tabs(["Dashboard", "Reports"])

with tab1:
    st.write("Dashboard Content")

with tab2:
    st.write("Reports Content")
```

## Expander

```python
with st.expander("See Details"):
    st.write("Hidden Content")
```

## Containers

```python
with st.container():
    st.write("Grouped UI elements")
```


# 📥 10. User Input Widgets

| Widget      | Example                          |
|-- |-- |
| Text Input  | `st.text_input()`                |
| Password    | `st.text_input(type="password")` |
| Number      | `st.number_input()`              |
| Slider      | `st.slider()`                    |
| Selectbox   | `st.selectbox()`                 |
| Multiselect | `st.multiselect()`               |
| Checkbox    | `st.checkbox()`                  |
| Radio       | `st.radio()`                     |
| Date        | `st.date_input()`                |
| File Upload | `st.file_uploader()`             |

Example:

```python
age = st.slider("Select Age", 18, 60)
hobbies = st.multiselect("Select Hobbies", ["AI", "ML", "Coding"])
```


# 11. Forms (Professional Input Handling)

```python
with st.form("login_form"):
    email = st.text_input("Email")
    password = st.text_input("Password", type="password")
    submit = st.form_submit_button("Login")

if submit:
    st.success("Form submitted")
```


# ⏳ 12. Status & Feedback Elements

```python
st.success("Success")
st.error("Error")
st.warning("Warning")
st.info("Information")
st.balloons()
st.snow()
```

## Progress Bar

```python
progress = st.progress(0)
for i in range(100):
    progress.progress(i + 1)
```


# 13. Caching

## Cache Data

```python
@st.cache_data
def load_data(file):
    return pd.read_csv(file)
```

## Cache Resources

```python
@st.cache_resource
def load_model():
    return heavy_model_load()
```

# 14. File Upload & Download

## Upload

```python
file = st.file_uploader("Upload CSV")

if file:
    df = pd.read_csv(file)
    st.dataframe(df)
```

## Download

```python
st.download_button(
    label="Download CSV",
    data=df.to_csv(index=False),
    file_name="data.csv",
    mime="text/csv"
)
```


# 15. Simple Authentication Pattern

```python
if "logged_in" not in st.session_state:
    st.session_state.logged_in = False

if st.button("Login"):
    if email == "admin" and password == "1234":
        st.session_state.logged_in = True

if st.session_state.logged_in:
    st.success("Welcome!")
```

# 16. Multipage Applications

Create a `pages/` folder:

```
pages/
    1_Dashboard.py
    2_Settings.py
```

Streamlit automatically detects and builds navigation.


# 17. Secrets Management

Create:

```
.streamlit/secrets.toml
```

Example:

```toml
API_KEY = "your_api_key"
```

Access in app:

```python
st.secrets["API_KEY"]
```


# 18. Deployment

## Option 1: Streamlit Community Cloud

* Push to GitHub
* Connect repository
* Deploy

## Option 2: Docker

## Option 3: AWS / GCP / Azure
