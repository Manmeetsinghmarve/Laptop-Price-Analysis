# Laptop-Price-Analysis
### Project Report: Comprehensive Laptop Price Analysis

## 1. Introduction

This project undertakes a comprehensive Exploratory Data Analysis (EDA) of a laptop dataset to uncover factors influencing laptop pricing. The objective is to identify relationships between specifications (e.g., RAM, CPU, GPU, storage, screen features), brand, operating system, and the final price. These insights are invaluable for consumers making purchasing decisions, manufacturers optimizing product lines, and retailers strategizing pricing.

## 2. Data Loading and Preparation

The analysis begins by loading the `laptop_prices.csv` dataset. Thorough data cleaning and preprocessing steps were essential:

* **Loading Data**: The dataset is loaded, and initial checks (`df.info()`, `df.describe()`, `df.head()`) are performed to understand its structure, data types, and summary statistics. The dataset contains columns such as `Company`, `Product`, `TypeName`, `Inches`, `Ram`, `OS`, `Weight`, `Price_euros`, and various specifications for screen, CPU, GPU, and storage.
* **Feature Extraction and Cleaning**:
    * **Screen Resolution**: `ScreenW` and `ScreenH` are extracted from the `Screen` column.
    * **CPU**: `CPU_company` is extracted from the `Cpu` column.
    * **GPU**: `Gpu_Company` is extracted from the `Gpu` column.
    * **Storage**: `Storage_Type` and `Storage_Value` (in GB) are extracted and standardized from the `Storage` column. This includes splitting `Storage` into `SSD` and `HDD` components where applicable.
    * **RAM**: `Ram` is converted to numeric (if not already) and `GB` is removed.
    * **Weight**: `Weight` is converted to numeric and 'kg' is removed.
    * **Price**: `Price_euros` is ensured to be in numeric format.
* **Categorical Encoding**: `Touchscreen` and `RetinaDisplay` are converted to integer (0 or 1) from 'Yes'/'No' string values. `IPSpanel` is also similarly converted.
* **New Feature Creation**:
    * `Screen_Resolution_Density`: Calculated based on screen width and height.
    * `Screen_Size_Category`: Categorizes laptops based on `Inches` (e.g., 'Small', 'Medium', 'Large').
    * `Price_Category`: Categorizes laptops into price ranges (e.g., 'Low', 'Mid', 'High').

## 3. Exploratory Data Analysis (EDA) - Key Findings

The EDA reveals various significant insights into laptop pricing and features:

### 3.1 Price Distribution

* **Overall Price Range**: The distribution of `Price_euros` generally shows a wide range, often skewed towards lower to mid-range prices, with a long tail extending to very expensive models.
* **Insight**: This distribution helps understand the market's general price points and identifies segments with high competition or premium offerings.

### 3.2 RAM vs. Price

* **Positive Correlation**: A clear positive correlation exists between `Ram` size and `Price_euros`. Laptops with higher RAM capacities tend to be more expensive.
* **Insight**: RAM is a significant determinant of laptop cost, indicating its importance for performance and the premium users are willing to pay for it.

### 3.3 Laptop Type vs. Price

* **Type-Specific Pricing**: Different `TypeName` categories (e.g., 'Gaming', 'Ultrabook', 'Workstation') exhibit distinct price distributions. Gaming laptops and Workstations are typically among the most expensive, while Netbooks or Convertibles might be cheaper.
* **Insight**: The intended use and performance capabilities heavily influence a laptop's price segment.

### 3.4 Company Distribution and Pricing

* **Market Share vs. Price**: While some companies might dominate in terms of market share (number of models), their average prices can vary significantly. Some brands command higher prices across their product lines.
* **Insight**: Brand perception and target market strategy play a role in pricing. The `Laptop Price Analysis.md` explicitly shows the top 10 companies by product count.

### 3.5 Top 10 Most Expensive Laptops

* **Premium Models**: Identifying the top 10 most expensive laptops highlights specific high-end products and their associated brands and specifications.
* **Insight**: This showcases the ultra-premium segment of the market and the features that command the highest prices.

### 3.6 Operating System Distribution

* **OS Popularity**: The distribution of `OS` reveals the most popular operating systems among the dataset's laptops (e.g., Windows, macOS, Linux).
* **Insight**: Windows typically dominates the market, but the presence and pricing of macOS and Linux devices indicate their respective market niches.

### 3.7 Screen Features vs. Price

* **IPS Panel and Retina Display**: Laptops featuring an `IPSpanel` or `RetinaDisplay` tend to have higher prices compared to those without.
* **Insight**: Advanced display technologies are perceived as premium features, justifying a higher price point.

### 3.8 CPU and GPU Company vs. Price

* **CPU Company Impact**: Laptops with Intel CPUs generally have a wide price range, while AMD might occupy a different segment.
* **GPU Company Impact**: Similarly, NVIDIA GPUs are often associated with higher-priced gaming and workstation laptops compared to integrated graphics or AMD GPUs.
* **Insight**: The choice of processor and graphics card manufacturers significantly impacts the laptop's performance capabilities and, consequently, its price.

### 3.9 Storage Type vs. Price

* **SSD Premium**: Laptops equipped with `SSD` storage (especially larger capacities or SSD-only configurations) tend to be more expensive than those relying solely on `HDD` or a combination.
* **Insight**: The faster performance and durability of SSDs command a premium in the market.

### 3.10 Screen Size and Resolution vs. Price

* **Screen Size and Price**: While a direct linear correlation isn't always strong, larger screen sizes or specific optimal sizes might be associated with higher price points, often due to being paired with other high-end components.
* **Screen Resolution vs. Price**: Higher `Screen_Resolution_Density` (e.g., 4K vs. Full HD) is associated with higher prices.
* **Insight**: Enhanced visual experience features contribute to the overall cost.

## 4. Conclusion

This comprehensive EDA highlights that laptop pricing is a complex interplay of various factors. **RAM, storage type (SSD premium), CPU/GPU performance (Intel/NVIDIA dominance in high-end), screen features (IPS, Retina, high resolution), and laptop type (Gaming, Workstation)** are the most significant drivers of price. While brand and operating system play a role, core hardware specifications and the intended use-case of the laptop explain most of the price variance. Understanding these dynamics is crucial for making informed purchasing decisions and for businesses aiming to effectively position their products in the competitive laptop market.

## 5. Recommendations

Based on the analysis, consider the following:

* **For Consumers**: Prioritize RAM and SSD storage for performance. Be prepared to pay a premium for gaming or workstation laptops and for advanced display technologies.
* **For Manufacturers**: Focus on optimizing the balance of RAM, storage, and CPU/GPU to meet specific price points and target customer segments. Emphasize advanced screen features in premium models.
* **For Retailers**: Segment inventory by key price drivers like RAM, storage, and CPU/GPU to cater to different customer budgets and performance needs. Highlight premium screen features for high-end sales.

## 6. Future Work

Further analysis could include:

* **Price Prediction Model**: Develop a machine learning model to predict laptop prices based on its specifications.
* **Sentiment Analysis**: Analyze user reviews to understand customer satisfaction and how it correlates with price and features.
* **Time Series Analysis**: If historical data were available, analyze how laptop prices and feature trends evolve over time.
* **Market Segmentation**: Deeper segmentation of the market based on buyer personas and their specific needs and budget constraints.
