# Heterogeneity Index

As a way to recognize candidate for well intervention or workover jobs, using historical production data, we can create an analysis that creates a dimensionless calculated variable used to compare the behavior of individual wells in a group, using the average behavior of the group of wells as reference. Or widely known as **Heterogeneity Index**

![alt text](https://github.com/aulanaufal/HeterogeneityIndex/blob/master/HI_Formula.png?raw=true)

* HI = 0 are the wells that behaves like the average
* HI > 0 are the wells that behaves above the average
* HI < 0 are the wells that behaves below the average

But to know more about how the behavior changes along the production lifetime of a well, we need to calculate *calculate the cumulative of the heterogeneity index.* Then, we can plot the cum HI values of 2 variables (e.g. oil and water) in a scatter plot for each date to see anomalous behavior.

![alt text](https://github.com/aulanaufal/HeterogeneityIndex/blob/master/HI_Plot_Example.png?raw=true)

Each point on the above plot represents one well on a certain date. It is 2 heterogeneity analysis against each other, the running sum of the water HI vs the running sum of the oil HI. There will be 4 quadrants (where each well we can color code based on the latest date quadrant) that we can use as an analysis method for early stage of workover/well intervention opportunity identification:

* __Region of High Water and Low/High Oil__: Wells need further investigaton on water problems. Could be candidate for WSO jobs
* __Region of Low Water and Low Oil__: Wells need further investigation on its surrounding reservoir properties or completion. Could be candidate for acidizing/stimulation
* __Region of Low Water and High Oil__: Wells are high oil producer, no further action needed

Beside its quadrant, the trace lines can also give us insight. Wells that were previously inside the Low Water quadrant but at some point rapidly changes to High water quadrants could be a sign of water encroachment problems (Coning/Cusping, Channeling, Casing/Tubing/Packer leaks, Flow behing Casing, Moving WOC, Watered Out Layer, etc.)

Conventional HI can give extreme values (between -1 and infinity, i.e. it can be very high should the well is far above average). From [SPE-138229-MS](https://doi.org/10.2118/138229-MS), the paper proposed a modified version that normalize the monthly HI values

![alt text](https://github.com/aulanaufal/HeterogeneityIndex/blob/master/MHI_Formula.png?raw=true)

# Inside the Notebook

We can found a python code which takes data from a .csv that contains each well's daily oil and water production rate along with the reservoir sand it produces. It then calculates the __cum MHI__ for oil and water for each respective reservoir sand (since reservoir layer can be a determining factor that differentiate production performance, a logical approach is to filter each sand separately and analyze the HI plot by sand). Finally, we can have a HI scatter plot and play with different dates from the slider

![alt text](https://github.com/aulanaufal/HeterogeneityIndex/blob/master/MHI_Plot.jpg?raw=true)

## Improvements

As we can see above, there are several insights that we can get from adding the trace line. Feel free to create a pull request to plot the trace line!

# Citation

Should you use this repository, please make this citation:

> Naufal, A.A., Heterogeneity Index, (2020), GitHub Repository, https://github.com/aulanaufal/HeterogeneityIndex

Bibtex: Coming Soon

# License 

```
MIT License

Copyright (c) [year] [fullname]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```




