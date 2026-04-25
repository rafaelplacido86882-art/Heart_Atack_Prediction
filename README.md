# A classification project
در این پروژه شما با توجه به اطلاعات پزشکی یک بیمار که در ادامه به صورت کامل شرح داده شده است پیش بینی میشود که یک بیمار شانس کمی برای حمله قلبی دارد یا شانس زیادی؟!
داده ها درون فایل
heart.csv
ذخیره شده اند.# hello world!

print('hello world')
atack cardiac a amelia ema andrade adan ema andrade erick ema andrade gregorio rodrigez gonzalez ulices rodrigez gonzalez romelia ema jose andrade   children alexander ema alexander andrade   
amelia ema andrade children beyby atack cardiac heart The main cause of the heart attack is coronary artery disease. It is one of the most common heart diseases. The cause of coronary heart disease is plaque, which is a substance that builds up inside arteries and blocks the supply of oxygen-saturated blood to the heart. This buildup is called atherosclerosis, and the insufficient blood flow saturated with oxygen coming to the heart is called ischemia.

Plaque rupture (the rapture of the tissue covering the plaque) can then happen, which leads to blood clots, blocking the arteries even more. Hypoxia is the lack of oxygen in the organs itself, including the heart. Thus, in our context, all this terminology is almost the same.

Unhealthy Habits and Other Factors of Atherosclerosis
The main factors that increase the risk of plaque buildup:

unhealthy diet
smoking
lack of physical activity
diabetes
high cholesterol
age
and others

Heart-Attack-Analysis-Causes
Heart Failure
Heart attack is one of the leading causes of heart failure, which is when the heart cannot supply enough blood to the organs of the body. When a heart attack happens, it can lead to necrosis (death of the myocardium – tissue of the heart). Building necrosis can eventually lead to heart failure.

LightningChart Python
Feature-image---lcpy-social-media
For this task, we use the LightningChart Python library. It provides a wide range of tools for creating graphs that can be useful for heart attack analysis and predictions in Python. In this project, we will use:

XY Charts (Link to docs)
In combination with Point Series (Link to docs)
Grouped Bar Chart (Link to docs)
Box Plots (Link to docs)
LightningChart provides easily-to-initialize charts that are also easily and widely customizable, so we will use this library for the visualizations.

Setting Up Python Environment
To create a heart attack analysis application in Python, first, we need to set up our Python environment.

1. The first step is installing Homebrew itself
I recommend using Homebrew package manager as it is popular and has a lot of packages. Moreover, it is arguably more convenient than installing Python using .dmg. You can skip this step if it is already installed on your Mac. Enter Terminal app and copy/paste this string:

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
Copy Code
Important note: the installation of Homebrew is not fast, it usually takes between 5 to 15 minutes.

2. Installation of Python
This command will install the latest stable version of Python. 

brew install python
Copy Code
NOTE: if you don’t want to use Homebrew, you can access the official Python website, select the latest stable version downloader for MacOS (its named macOS 64-bit universal2 installer), and follow the installation instructions. You can check the version using python3 –version in the terminal. If it displays Unknown command error, it is most likely due to PATH variables. Refer to this guide to fix it.

Installation of Python on Windows
I recommend using the tool Winget. To install the Python package, open cmd or PowerShell as Administrator and type:

winget install Python.Python.3
Copy Code
NOTE: if you don’t want to use Winget, You can access the official Python website, select the latest stable version downloader for Windows
(it is named Windows installer (64-bit)) and follow the installation instructions. You can verify the installation of Python and pip by typing python --version and pip --version respectively. If it displays command' is not recognized error, it is most likely due to PATH variables. Refer to this guide to fix.

3. Installation of IDE
For IDE (integrated development environment), I recommend using PyCharm as it is clean and powerful. However, the full version is paid so you can also use VSCode. Optionally, you may want to set up Venv (Python virtual environment) to install packages there and not clutter the Python installation. The environment-creating instructions are:

PyCharm – https://www.jetbrains.com/help/pycharm/creating-virtual-environment.html#python_create_virtual_env
VSCode – https://code.visualstudio.com/docs/python/environments
4. Setting up jupyter notebook
For PyCharm (ONLY PROFESSIONAL VERSION): Just create an .ipynb file and start coding. The IDE will install everything needed on its own.

ipynb_create
For Visual Studio Code

Install Jupyter extension:
jupyter_extension
Select and open the working directory
Create venv (⇧⌘P or Ctrl-⇧-P). Very recommended!
Refer to the following article (starting from “Workspace Trust” paragraph)
5. Libraries Used
Jupyter: A very nice library for data analysis, supports both executable code blocks and markdown blocks. With it, you can create clear and visual analysis reports.
Pandas: In this project, we will mainly use the two-dimensional data frame data structure provided by Pandas. It can be easily created from a .CSV or Excel file.
NumPy: NumPy is provided with Pandas and it is a fundamental package for scientific computing in Python. It provides support for arrays, mathematical functions, and linear algebra operations.
LightningChart: LightningChart is the main library used in the project for creating different types of charts in Python. It provides highly customizable graph-building tools, including simple XY charts, 3D charts, Bar charts, Spider charts, and Map charts.
6. Installing and importing libraries
Type in terminal to install libraries:

pip install pandas lightningchart
Copy Code
Abstract: Basics of Jupyter Notebooks
Jupyter notebooks are very useful for data analysis tasks. Basically, in our case, you can call Jupyter an “IDE inside an IDE”. With it, you can create .ipynb type files which are convenient for doing anything with data.

So what are the advantages of it, instead of the regular Python files? (those with .py extension)

Jupyter supports code block, the execution of which can be done separately. This means that if one block is executed, the results persist (until restarting the kernel), thus you can for example, put your imports in the first block, and forget about them.
You can include markdown type blocks (the same format as this README is written in) to write concise annotations.
As you can execute blocks separately, you can get program outputs after each of these blocks for visual purposes.
For these reasons, Jupyter notebooks are visual and good for demonstration (it is often what we aim for when doing data analysis).

Loading and Processing Data
Note that you can see the complete code files in GitHub, here will be the summary. Before everything, we need to import required libraries:

import pandas as pd
import lightningchart as lc
Copy Code
Then, we use read_csv method from pandas library (if we had .xslx, we would have used read_excel). If you type the variable0s name last in the block, it would be output, this is Jupyter NB feature.

df = pd.read_csv('data/heart.csv')
df
Copy Code
Remember to always check data consistency – for data types and null values
These methods can be in handy:

df.dtypes – for checking data types of the data frame
df.isnull().sum() – for checking the number of null values in each column
See .ipynb file for complete data processing and a more detailed explanation.

Data Analysis
For the Multi-Variable analysis, the most common method of performing multi-variable analysis is the correlation matrix, and a scatter plot (sometimes heatmaps). But at first, as we are using LightningChart, we have to use the license key:

with open("license_key.txt", "r") as file:  # License key is stored in 'license_key.txt'
    key = file.read()
lc.set_license(key)
Copy Code
Note! Always remember not to leak your keys when you share code! I recommend using a file and including it in .gitignore, or session variables. This is a correlation matrix:

numeric_columns = ['age', 'trtbps', 'chol', 'thalachh', 'oldpeak']
data_numeric = df[numeric_columns]
data_numeric.corr()
Output:
               age    trtbps      chol  thalachh   oldpeak
age       1.000000  0.279351  0.213678 -0.398522  0.210013
trtbps    0.279351  1.000000  0.123174 -0.046698  0.193216
chol      0.213678  0.123174  1.000000 -0.009940  0.053952
thalachh -0.398522 -0.046698 -0.009940  1.000000 -0.344187
oldpeak   0.210013  0.193216  0.053952 -0.344187  1.000000
Copy Code
Numbers here represent the strength of correlation:

0.7 to 1.0 (-0.7 to -1.0) -> Strong correlation.
0.5 to 0.7 (-0.5 to -0.7) -> Moderate correlation.
0.3 to 0.5 (-0.3 to -0.5) -> Weak correlation.
0.0 to 0.3 (0.0 to -0.3) -> Negligible correlation.
Positive numbers mean positive correlation (as one value increases, the other does too). Negative numbers mean a negative correlation (as one value increases, the other decreases). Now, we can start plotting the charts. For this task, we are using LightningChart Python. It is a library designed for dealing with huge (flowing) amounts of data. However, it is also usable for data analysis, and we will use its features here.

chol_neg = df.loc[df['output'] == 0, 'chol'].tolist()  # get the cholesterol vals where output is 0 (no heart attack)
heartrate_neg = df.loc[df['output'] == 0, 'thalachh'].tolist()  # get the cholesterol vals where output is 0 (no heart attack)
chol_pos = df.loc[df['output'] == 1, 'chol'].tolist()  # same thing with 1
heartrate_pos = df.loc[df['output'] == 1, 'thalachh'].tolist()
scatter = lc.ChartXY(   # scatter chart intialization
    theme=lc.Themes.White,  # overall theme
    title='Scatter Chart (Cholesterol vs Heartrate)', 
)
series_neg = scatter.add_point_series().add(
    x=chol_neg,  # push samples to series
    y=heartrate_neg,
)
series_pos = scatter.add_point_series().add(
    x=chol_pos,  
    y=heartrate_pos,
)
series_neg.set_point_color(lc.Color(0, 255, 0, 192)).set_name("No Heart Attack")  # set colors for points
series_pos.set_point_color(lc.Color(255, 0, 0, 192)).set_name("Heart Attack")
scatter.get_default_x_axis().set_title("Cholesterol")
scatter.get_default_y_axis().set_title("Heartrate")
scatter.add_legend().add(scatter)
scatter.open()
Copy Code
Heart-Attack-Analysis-Cholesterol
It can be seen that the higher the heart rate, the more risk of a heart attack. Also, we can see that generally, the higher the cholesterol, the higher the heart rate. The correlation between cholesterol and the output is not very obvious. Note: see .ipynb file for more details.

Heart Rate & Exercise-Induced Angina Correlation Analysis
We can use a Box Plot for this analysis:

heartrate_angina = df.loc[df['exng'] == 1, 'thalachh'].tolist()
heartrate_noangina = df.loc[df['exng'] == 0, 'thalachh'].tolist()
boxplt_chol = lc.BoxPlot(  
    data=[heartrate_noangina, heartrate_angina],
    theme=lc.Themes.White,
    title='Heartrate',
    xlabel='No Angina (Left), Angina (Right)',
    ylabel='Values'
)
boxplt_chol.open()
Copy Code
Heart-Attack-Analysis-boxplot
It is also useful to get the mean values of each column:

thalach_exang_mean = df.groupby('exng')['thalachh'].mean()
print("Mean Maximum Heart Rate by Exercise-Induced Angina:")
print(thalach_exang_mean)
Output:
Mean Maximum Heart Rate by Exercise-Induced Angina:
exng
0    155.681373
1    137.212121
Name: thalachh, dtype: float64
Copy Code
It can be seen that individuals with exercise-induced angina have a lower mean maximum heart rate. It suggests that these individuals may experience cardiovascular limitations. Angina is typically a sign that the heart muscle is not getting enough oxygen-rich blood during exertion, which could prevent these individuals from reaching higher heart rates.

Box Plot for Cholesterol
Heart-Attack-Analysis-boxplot-cholesterol
(All boxplots can be created analogically to the Heartrate one – just change the column name). We can see that the extreme number of cholesterol relates to heart attack, but it is not necessary that those who have lower cholesterol are not subject to heart attacks.

Box Plot for Blood Pressure
Heart-Attack-Analysis-blood-pressure
Those who had a heart attack generally have lower blood pressure values. It may be counterintuitive, but it shows that blood pressure alone doesn’t certainly show that the individual is subject to a heart attack or not.

Grouped Bar Chart
Another type of chart for single variable analysis is (grouped or stacked) bar chart. Here is an example:

bins = [29, 50, 60, 77]  
labels = ['29-50', '51-60', '61-77']
df['age_range'] = pd.cut(df['age'], bins=bins, labels=labels, right=True)
mapping = {0: 'No Heart Attack', 1: 'Heart attack'}
df['output_words'] = df['output'].map(mapping)
outcome_counts_by_age = df.groupby(['age_range', 'output_words'], observed=True).size().unstack(fill_value=0)
result = []
for target in df['output_words'].unique():  # make json-like formation of data
    values = [int(x) for x in outcome_counts_by_age[target].tolist()]  
    result.append({                     
        'subCategory': target,
        'values': values
    })
barchart_grouped = lc.BarChart(  # initialize bar chart
    vertical=True,
    theme=lc.Themes.White,
    title='Heart Attacks By Age',
)
barchart_grouped.set_data_grouped(labels, result)  # set data
barchart_grouped.set_sorting('alphabetical').set_animation_category_position(False)
barchart_grouped.add_legend().add(barchart_grouped)  # add legend
barchart_grouped.open() 
Copy Code
Heart-Attack-Analysis-attacks-by-age
Conclusion
Extreme numbers of cholesterol likely lead to heart attacks

سن فرد (Age)
، جنسیت (Sex)
، آیا درد با فعالیت خاصی شروع میشود؟  (exang)
: عدد یک یعنی بله-
عدد صفر یعنی خیر
، تعداد رگهای اصلی (ca)
: مقداری از صفر تا سه
، نوع درد قفسه سینه (cp)
مقدار ۱ : درد مستقیم قلبی -
مقدار ۲ : درد غیرمسقیم که منجر به حس کردن درد در قلب میشود-
مقدار ۳ : درد غیر قلبی -
مقدار ۴ : بدون علایم
، فشارخون در حال استراحت (trtbps)
، چربی خون (chol)
، قند خون ناشتا بالا – دیابت (fbs)
: مقدار یک : دارد -
مقدار صفر : ندارد
، نتیجه نوار قلب در حال استراحت (rest_ecg)
مقدار صفر : نرمال -
مقدار یک : بخش ST نوار قلب غیر طبیعی است -
مقدار دو : احتملا یا قطعا بطن چپ بزرگ است 
، حداکثر ضربان قلب (thalach)
، شانس حمله قلبی (target)
مقدار صفر : شانس کم -
مقدار یک : شانس زیاد 
