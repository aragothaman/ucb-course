
![[Pasted image 20260725182847.png]]


As a final step in the process, you should be able to validate that the data meets your project’s requirements. At this point, you should have the ability to run descriptive statistics on the data to ensure that your dataset meets established best practices. You should also consider visualizing the data to determine any additional insights that might impact your project before proceeding.

During data preprocessing, several descriptive statistics are commonly used to understand the characteristics of the data. These statistics provide insights into the distribution, central tendency, and variability of the data. Some of the key descriptive statistics used in data preprocessing include:

- **Mean:** The average value of the data, calculated as the sum of all values divided by the number of values. Using NumPy, **_mean()_** is used for calculating the mean.
- **Median**: The middle value of the data when it is sorted in ascending or descending order. It is less affected by outliers than the mean. **_median()_** is used for calculating the median.
- **Mode**: The most frequently occurring value in the data. It can also be used for categorical data.
- **Standard deviation:** A measure of the dispersion of the data points around the mean. It indicates how spread out the values are from the average. **_std()_** is used for calculating the standard deviation.
- **Variance**: The average of the squared differences from the mean. It quantifies the spread of the data. np.var() is used for calculating the variance.
- **Range:** The difference between the maximum and minimum values in the data. It provides a measure of the spread of the data.
- **Percentiles:** Values that divide the data into 100 equal parts. For example, the 25th percentile (also known as the first quartile) is the value below which 25% of the data falls. np.percentile() is used for computing the percentiles.
- **Skewness:** A measure of the asymmetry of the distribution of the data. Positive skewness indicates a tail to the right, while negative skewness indicates a tail to the left. Use **_stats.skew()_** to calculate the skewness of an array.
- **Kurtosis:** A measure of the peak for the distribution of the data. Higher kurtosis indicates a sharper peak around the mean. Use **_scipy.stats.kurtosis()_** to calculate the kurtosis of an array.