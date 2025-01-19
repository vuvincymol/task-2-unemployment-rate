# task-2-unemployment-rate
Unemployment Analysis with Python


Author: Vincy Mol V U

Domain: Data Science


Import tools for data work and making charts (like pandas, matplotlib ,eaborn).
import plotly.express as px: Imports the plotly.express module, used to create interactive visualizations. px is a shortcut.
Data Handling

from google.colab import files: Imports the files module, which is used to upload files to your Colab notebook.
uploaded = files.upload(): Uploads files from your local machine.
data = pd.read_csv('/content/Unemployment in India.csv'): Reads the data from the CSV file into a pandas DataFrame called data.
data = pd.read_csv('/content/Unemployment_Rate_upto_11_2020.csv'): Reads data from another CSV file, potentially updating or replacing the existing data in the data DataFrame.


print(data.head()): Displays the first few rows of the DataFrame to get a quick overview of the data.

print(data.isnull().sum()): Checks for missing values (NaN) in each column and prints the total number of missing values.
data.columns = ['States', 'Date', 'Frequency', 'Estimated Unemployment Rate', 'Estimated Employed', 'Estimated Labour Participation Rate', 'Region', 'Longitude', 'Latitude']: Assigns new column names to the DataFrame to make them more descriptive.
Visualization

plt.title('Indian Unemployment'): Sets the title of the plot.
sns.histplot(x='Estimated Unemployment Rate', hue='Region', data=data): Creates a histogram of the 'Estimated Unemployment Rate' column, with different colors for each 'Region'.
plt.show(): Displays the plot.
umemployment = data.groupby(['Region', 'States'])['Estimated Unemployment Rate'].mean().to_frame(): Groups the data by 'Region' and 'States', calculates the mean unemployment rate for each group, and converts it into a new DataFrame.
figure = px.sunburst(...): Creates an interactive sunburst chart using plotly.express, showing the hierarchical relationship between 'Region', 'States', and 'Estimated Unemployment Rate'.
figure.show(): Displays the interactive sunburst chart.
