Here is the updated script. I have expanded **Section 1** significantly to break down the "Anatomy of a Plotting Command," specifically highlighting the difference between how you talk to **Matplotlib** versus how you talk to **Seaborn**, as this is the most common point of confusion for students in Week 5.

---

# Week 5 Lab Script: Exploratory Data Analysis (EDA)

**Video Start**

**[Intro]**

All right, welcome back everyone. We are rolling into **Week 5**, and we are tackling **Exploratory Data Analysis**, or EDA.

So, if Lab 4 was about "cleaning the house"—getting the data loaded, fixing the types, dealing with the mess—Lab 5 is about actually living in the house. It's about looking around and understanding what you bought.

We are using the same **San Francisco Rent dataset** as last week. So you should be familiar with the columns. But this time, we aren't just checking if the data is *broken*; we are checking what the data is *saying*.

**[Section 1: The "Big Three" Packages]**

Before we dive into the charts, let's talk about the tools in your belt. You’ll see three main imports at the top, and you need to know who does what:

1. **Pandas (`pd`):** This is your data container. It holds the Excel-like grid.
2. **Matplotlib (`plt`):** This is the "Grandfather" of Python plotting. It builds the canvas. It’s powerful, but the syntax can be a little clunky.
3. **Seaborn (`sns`):** This is the "Artist." It’s built *on top* of Matplotlib. It makes the charts look modern and handles a lot of the complex statistics for you.

You’ll also see `ydata_profiling`. That’s the "cheat code" that auto-generates a report. Run it, be amazed by it, but for this lab, you need to build the charts manually to learn the syntax.

**[Section 2: The Anatomy of a Syntax]**

Now, I want to slow down and look at **how** we actually tell Python to make a graph. A lot of students copy-paste code without knowing where the pieces go.

There are two "styles" you will see in this lab.

**Style A: The Matplotlib Style (Direct approach)**

When you use `plt.hist()`, look at the parentheses.

* **Where is the data?** You pass the specific column *directly* inside the brackets: `df['price']`.
* **Where are the options?** You add them as arguments after the comma, like `bins=30`.

**Style B: The Seaborn Style (Declarative approach)**

Seaborn is a bit more readable. Look at a command like `sns.scatterplot(x='sqft', y='price', data=df)`.

* **The Function:** The "type" of plot is decided by the function name itself—`scatterplot`, `barplot`, `boxplot`.
* **The Data Source:** You tell it explicitly: `data=df`. This says, "Look in the dataframe named `df`."
* **The Columns:** Because you pointed to `df`, you don't need to type `df['price']`. You just use the string `'price'` for `y` and `'sqft'` for `x`. It knows where to look.

**[Section 3: Decorating the Plot (Labels & Axes)]**

Now, here is the trick. You create the graph with **Seaborn**, but you dress it up with **Matplotlib**.

Since Seaborn draws *onto* a Matplotlib canvas, we use `plt` commands to fix the labels.

* `plt.title("...")`: This puts the text at the top.
* `plt.xlabel("...")` & `plt.ylabel("...")`: This labels your axes. **Always** do this. "Price" is meaningless unless we know if it's Monthly or Yearly.
* `plt.show()`: This is the "Print" button. It renders the final image.

So the workflow is:

1. **Seaborn** draws the data.
2. **Matplotlib** labels the axes.
3. **Matplotlib** shows the plot.

**[Section 4: Inspecting Data Quality]**

Okay, let's apply this. We start with **Part 2: Inspecting Data Quality**.
Run `df.describe()`.

I want you to look closely at the **Min** and **Max** columns.
Look at the `price` column. If the maximum rent is $10 million a month... is that a penthouse, or is that a typo?
Look at `sqft` (square footage). If the minimum is 0, does that make sense?

In the **"Try It Yourself"** section, identify these weird values. You don't need to fix them yet, just spot them.

**[Section 5: Univariate Analysis]**

Next, **Univariate Analysis**. One variable at a time.
We use **Histograms** for numbers (like Price) and **Bar Charts** for categories (like Neighborhood).

In the **Wrench section 🔧** for Part 4, you’ll create a histogram for `baths`.

* *Syntax Check:* Is `baths` a number? Yes. So we use `plt.hist(df['baths'])`.
* Then you need a bar chart for `sqft` by `baths`.
* *Syntax Check:* Now we have two variables. `sns.barplot(x='baths', y='sqft', data=df)`. See how we switched syntax because we switched tools?

**[Section 6: Bivariate Analysis]**

Finally, **Bivariate Analysis**. Relationships.

1. **Correlation Matrix:**
We use `df.corr()` to get the math, and `sns.heatmap()` to make it colorful.
Look for the dark squares—those are strong relationships.
2. **Scatterplot:**
This is `sns.scatterplot(x='sqft', y='price', data=df)`.
You are looking for a pattern. Is it a straight line? Is it a blob?
*Hint:* If you see a massive blob in the bottom left and one dot way up in the top right, that one dot is your outlier screwing up your scale.

**[Section 7: The Final Wrench & Reflection]**

For the final **Wrench section 🔧**:
I want you to Group By `year` and plot the average price.
Think about the syntax. You first need to create a *new* dataframe with `df.groupby('year')...` and *then* pass that new data into your plot.

And lastly, the **Reflection**.
Synthesize what you saw.

* Which variables mattered the most for price?
* Did the outliers make the graphs hard to read?

That is the workflow: **Load -> Inspect -> Univariate -> Bivariate -> Reflection.**
Jump into the Colab, look for the wrench emojis, and let's see what you find in the San Francisco housing market.

**[Video End]**