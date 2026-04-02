# 1. Title and Subheader
st.title("Sales Summary Dashboard")
st.subheader("Analyze product sales by category")

# 2. Create a hardcoded DataFrame (at least 5 rows, 3 columns)
data = {
    'Product': ['Laptop', 'Smartphone', 'Desk Chair', 'Monitor', 'Keyboard', 'Notebook'],
    'Category': ['Electronics', 'Electronics', 'Furniture', 'Electronics', 'Electronics', 'Stationery'],
    'Sales': [1200, 800, 150, 300, 50, 20]
}
df = pd.DataFrame(data)

# 3. Sidebar Filter (Task 2)
# We get unique categories for the selectbox
categories = df['Category'].unique()
selected_category = st.sidebar.selectbox("Select a Category to Filter:", categories)

# 4. Filter the data based on selection
filtered_df = df[df['Category'] == selected_category]

st.write(f"### Showing data for: {selected_category}")

st.dataframe(filtered_df)
st.line_chart(filtered_df['sales'])
