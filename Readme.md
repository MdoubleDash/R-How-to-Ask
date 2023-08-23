# How to ask a good R question?

---

<sup> This article is largely written based on </sup><sup>https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example</sup><sup> </sup>

You should include a [minimal reproducible example (MRE)](https://stackoverflow.com/help/minimal-reproducible-example) which enables others to exactly reproduce your issue on their machines.

**In short:**

1. Include a minimal dataset, necessary to demonstrate the problem (either by copying and pasting it into your script or preferably by using the `dput()` function to generate an R code to recreate it).
2. Share the minimal runnable code necessary to reproduce the issue, which can be run on the given dataset.
3. List the packages that are needed to run your code at the top of your script.
4. Describe your desired output in a clear and concise manner.

Here is an example:

___

### *How to get the conditional sum of two columns?*

*I am trying to get the sum of two columns in a data frame, while returning zero for the rows that have NA in one of the columns and return NA if both of the columns are NA for any specific rows. Here's what I have so far:*

```
# Required packages
library(dplyr)
library(tidyr)

# Data
df1 <- data.frame(x = c(1, 2, NA, 4, NA), y = c(6, NA, 8, 9, NA))

# Adding a column with the sum of x and y
df1 %>%
  mutate(z = replace_na(x + y, 0))
```

*How can I apply an if-statement to get my desired output as shown below?*

```
   x        y       z
   1        6       7
   2        NA      0
   NA       8       0
   4        9       13
   NA       NA      NA
```

___

In addition to the aforementioned steps, there are a few other things that can improve your question:

* Choose a clear and explanatory title for your question. Review [How do I write a good title?](https://meta.stackexchange.com/q/10647)
* Keep your example, both data and code, minimal while making sure it is reproducing the behavior, errors, etc. that you are seeing at your end.
* Include comments within your code to explain what it is that you are trying to achieve.
* [Format your question properly](/editing-help).
* [Use appropriate tags](/help/tagging). Remember to at least read the mouseover tooltip text on the tags you are using when asking a question.
* If you are using functions that are generating random numbers, use `set.seed()` to ensure reproducibility.
* If you have issues that are specific to your environment, include the version of R that you are using, the operating system that you are running on, and any other relevant information about your environment. Providing the output of `sessionInfo()` is helpful for these cases.

Moreover, you should **avoid**:

* Including details that are not necessary to address your issue.
* Pasting your [code, data, or errors as images](//meta.stackoverflow.com/a/285557).
* Sharing your code or data through [external links](https://meta.stackoverflow.com/questions/254428/).
* Asking a question before doing any research. Questions that show no attempt at solving the problem, are already answered here on Stack Overflow, and/or can easily be addressed with a simple Internet search tend to get negative feedback.
* Combining multiple questions into one post which would make your post too broad.
* Asking questions focused on statistics or data science. While there is some overlap between Stack Overflow and other technical communities, if your question is not about practical programming, you should explore other Stack Exchange communities, read their help pages, and consider posting to them instead of Stack Overflow.

Here are some additional helpful resources:

- Take [Stack Overflow's tour](https://stackoverflow.com/tour) and read [How to ask a good question](https://stackoverflow.com/help/how-to-ask)
- Review [How to make a great R reproducible example](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example)
- Read [Writing the perfect Question by Jon Skeet](https://codeblog.jonskeet.uk/2010/08/29/writing-the-perfect-question/)
