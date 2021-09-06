# House Price Prediction: Advanced Regression Techniques 

- The main aim of this project is to predict the house price based on various huge no of features 
- Predict sales prices and practice feature engineering, RFs, and gradient boosting

- Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

- With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

### Practice Skills
- Creative feature engineering 
- Advanced regression techniques like Linear regression, Lasso, ridge, random forest and gradient  etcboosting 


### Acknowledgments
- The Ames Housing dataset was compiled by Dean De Cock for use in data science education. It's an incredible alternative for data scientists looking for a modernized and expanded version of the often cited Boston Housing dataset. 
    
    
### Goal
- It is your job to predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable. 

### Metric
- Submissions are evaluated on **Root-Mean-Squared-Error (RMSE)** between the logarithm of the predicted value and the logarithm of the observed sales price. 
- **Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.**

### Submission File Format
- The file should contain a header and have the following format:

            Id,SalePrice
            1461,169000.1
            1462,187724.1233
            1463,175221
            etc.



#### Dataset to downloaded from the below link
https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data



## Building Machine Learning Pipelines: Data Analysis Phase

Here we are creating Machine Learning Pipelines considering all the life cycle of a Data Science Projects. 

> This is Regression Problem, so we will use Regression models like below and use related evaluation matrics

          1. Linear Regression
          2. Robust Regression
          3. Ridge Regression
          4. KERNEL Ridge Regression
          5. LASSO Regression
          6. Elastic Net
          7. Polynomial Regression
          8. Gradient Boosting Regressor
          9. Stochastic Gradient Descent (SGD)
          10. Random Forest Regressor
          11. Support Vector Machine Regression
          12. XGBOOST
          13. lightgbm
          14. Artificial Neaural Networks

## Lifecycle In A Data Science Projects
1. Data Analysis(EDA)/ Data Cleaning
2. Feature Engineering 
    - Null Handling,Outlier Handling, Numeric and Categorical feature handling, Sacling
3. Feature Selection
4. Model Building
5. Model Evaluation
6. Finalize Best model
7. Apply same model to Test data, Rescale O/P back and Create Final Submission file
5. Upload Final Submission file in Kaggle or Model Deployment 

## Splitted these activities into 2 sets

1. This notepad will do all activities till preprocessing and Feature selctionIn 
2. "House_Price_Prediction_Model_Training_2" Notepad will do all Model build, evaluation and Final submission file cration


#### In Data Analysis We will Analyze To Find out the below stuff
1. Check any Missing Values
2. All The Numerical Variables
3. Temporal Variables(Eg: Datetime Variables)¶
4. Distribution of the Numerical Variables (Discret and Continous)
5. Categorical Variables 
6. Cardinality of Categorical Variables (How many distinct categories in categorical feature)
7. Outliers Check (This is not used for discrete variable, only for Continous variable)
8. Relationship between independent and dependent feature(SalePrice)
9. Target variable analysis
10. Check correlation 


## Feature Engineering

### 1. Before Train and test  merge:

1. Only in Train Outlier handling: Remove outlier (Its not good practice, here only 2 extreme values , so deleted)

2. Target variable analysis -  Make it to Normal Distribution by log transformation

[ **This train test merge and apply all FE only done in kaggle kind competation. In real world scenario, we wont be knowing test  and leads to data leakage also**]


## 2. After Train and test  merge:
- We will be performing all the below steps in Feature Engineering

1. Missing values Handling
2. Temporal variables Conversion  -- Like Year,Yr data to Numeric differenced data based on Year_sold
3. Numerical Variables - Since the numerical variables are skewed we will perform log normal distribution
4. Categorical variables: remove rare labels and replaced as 'Rare_var'
5. Convert Categorial varible to Numeric (Not using one hot encoding)
6. Skewed Numerical features  - Box Cox Transformation of (highly) skewed features
	- For linear regression, data should be ND, but here features are skewed little. By this Box Cox Transformation we converted to ND

7. Standarise the values of the variables to the same range - MinMax Scalar (0-1) 
	- But here we didnt do scalarization, Reason: after Box Cox Transformation All feature looked like scarized

## File descriptions

    train.csv - the training set
    test.csv - the test set
    data_description.txt - full description of each column, originally prepared by Dean De Cock but lightly edited to match the column names used here
    sample_submission.csv - a benchmark submission from a linear regression on year and month of sale, lot square footage, and number of bedrooms


## Data fields
        Here's a brief version of what you'll find in the data description file.

        SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict.
        MSSubClass: The building class
        MSZoning: The general zoning classification
        LotFrontage: Linear feet of street connected to property
        LotArea: Lot size in square feet
        Street: Type of road access
        Alley: Type of alley access
        LotShape: General shape of property
        LandContour: Flatness of the property
        Utilities: Type of utilities available
        LotConfig: Lot configuration
        LandSlope: Slope of property
        Neighborhood: Physical locations within Ames city limits
        Condition1: Proximity to main road or railroad
        Condition2: Proximity to main road or railroad (if a second is present)
        BldgType: Type of dwelling
        HouseStyle: Style of dwelling
        OverallQual: Overall material and finish quality
        OverallCond: Overall condition rating
        YearBuilt: Original construction date
        YearRemodAdd: Remodel date
        RoofStyle: Type of roof
        RoofMatl: Roof material
        Exterior1st: Exterior covering on house
        Exterior2nd: Exterior covering on house (if more than one material)
        MasVnrType: Masonry veneer type
        MasVnrArea: Masonry veneer area in square feet
        ExterQual: Exterior material quality
        ExterCond: Present condition of the material on the exterior
        Foundation: Type of foundation
        BsmtQual: Height of the basement
        BsmtCond: General condition of the basement
        BsmtExposure: Walkout or garden level basement walls
        BsmtFinType1: Quality of basement finished area
        BsmtFinSF1: Type 1 finished square feet
        BsmtFinType2: Quality of second finished area (if present)
        BsmtFinSF2: Type 2 finished square feet
        BsmtUnfSF: Unfinished square feet of basement area
        TotalBsmtSF: Total square feet of basement area
        Heating: Type of heating
        HeatingQC: Heating quality and condition
        CentralAir: Central air conditioning
        Electrical: Electrical system
        1stFlrSF: First Floor square feet
        2ndFlrSF: Second floor square feet
        LowQualFinSF: Low quality finished square feet (all floors)
        GrLivArea: Above grade (ground) living area square feet
        BsmtFullBath: Basement full bathrooms
        BsmtHalfBath: Basement half bathrooms
        FullBath: Full bathrooms above grade
        HalfBath: Half baths above grade
        Bedroom: Number of bedrooms above basement level
        Kitchen: Number of kitchens
        KitchenQual: Kitchen quality
        TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)
        Functional: Home functionality rating
        Fireplaces: Number of fireplaces
        FireplaceQu: Fireplace quality
        GarageType: Garage location
        GarageYrBlt: Year garage was built
        GarageFinish: Interior finish of the garage
        GarageCars: Size of garage in car capacity
        GarageArea: Size of garage in square feet
        GarageQual: Garage quality
        GarageCond: Garage condition
        PavedDrive: Paved driveway
        WoodDeckSF: Wood deck area in square feet
        OpenPorchSF: Open porch area in square feet
        EnclosedPorch: Enclosed porch area in square feet
        3SsnPorch: Three season porch area in square feet
        ScreenPorch: Screen porch area in square feet
        PoolArea: Pool area in square feet
        PoolQC: Pool quality
        Fence: Fence quality
        MiscFeature: Miscellaneous feature not covered in other categories
        MiscVal: $Value of miscellaneous feature
        MoSold: Month Sold
        YrSold: Year Sold
        SaleType: Type of sale
        SaleCondition: Condition of sale


MSSubClass: Identifies the type of dwelling involved in the sale.	

        20	1-STORY 1946 & NEWER ALL STYLES
        30	1-STORY 1945 & OLDER
        40	1-STORY W/FINISHED ATTIC ALL AGES
        45	1-1/2 STORY - UNFINISHED ALL AGES
        50	1-1/2 STORY FINISHED ALL AGES
        60	2-STORY 1946 & NEWER
        70	2-STORY 1945 & OLDER
        75	2-1/2 STORY ALL AGES
        80	SPLIT OR MULTI-LEVEL
        85	SPLIT FOYER
        90	DUPLEX - ALL STYLES AND AGES
       120	1-STORY PUD (Planned Unit Development) - 1946 & NEWER
       150	1-1/2 STORY PUD - ALL AGES
       160	2-STORY PUD - 1946 & NEWER
       180	PUD - MULTILEVEL - INCL SPLIT LEV/FOYER
       190	2 FAMILY CONVERSION - ALL STYLES AND AGES

MSZoning: Identifies the general zoning classification of the sale.
		
       A	Agriculture
       C	Commercial
       FV	Floating Village Residential
       I	Industrial
       RH	Residential High Density
       RL	Residential Low Density
       RP	Residential Low Density Park 
       RM	Residential Medium Density
	
LotFrontage: Linear feet of street connected to property

LotArea: Lot size in square feet

Street: Type of road access to property

       Grvl	Gravel	
       Pave	Paved
       	
Alley: Type of alley access to property

       Grvl	Gravel
       Pave	Paved
       NA 	No alley access
		
LotShape: General shape of property

       Reg	Regular	
       IR1	Slightly irregular
       IR2	Moderately Irregular
       IR3	Irregular
       
LandContour: Flatness of the property

       Lvl	Near Flat/Level	
       Bnk	Banked - Quick and significant rise from street grade to building
       HLS	Hillside - Significant slope from side to side
       Low	Depression
		
Utilities: Type of utilities available
		
       AllPub	All public Utilities (E,G,W,& S)	
       NoSewr	Electricity, Gas, and Water (Septic Tank)
       NoSeWa	Electricity and Gas Only
       ELO	Electricity only	
	
LotConfig: Lot configuration

       Inside	Inside lot
       Corner	Corner lot
       CulDSac	Cul-de-sac
       FR2	Frontage on 2 sides of property
       FR3	Frontage on 3 sides of property
	
LandSlope: Slope of property
		
       Gtl	Gentle slope
       Mod	Moderate Slope	
       Sev	Severe Slope
	
Neighborhood: Physical locations within Ames city limits

       Blmngtn	Bloomington Heights
       Blueste	Bluestem
       BrDale	Briardale
       BrkSide	Brookside
       ClearCr	Clear Creek
       CollgCr	College Creek
       Crawfor	Crawford
       Edwards	Edwards
       Gilbert	Gilbert
       IDOTRR	Iowa DOT and Rail Road
       MeadowV	Meadow Village
       Mitchel	Mitchell
       Names	North Ames
       NoRidge	Northridge
       NPkVill	Northpark Villa
       NridgHt	Northridge Heights
       NWAmes	Northwest Ames
       OldTown	Old Town
       SWISU	South & West of Iowa State University
       Sawyer	Sawyer
       SawyerW	Sawyer West
       Somerst	Somerset
       StoneBr	Stone Brook
       Timber	Timberland
       Veenker	Veenker
			
Condition1: Proximity to various conditions
	
       Artery	Adjacent to arterial street
       Feedr	Adjacent to feeder street	
       Norm	Normal	
       RRNn	Within 200' of North-South Railroad
       RRAn	Adjacent to North-South Railroad
       PosN	Near positive off-site feature--park, greenbelt, etc.
       PosA	Adjacent to postive off-site feature
       RRNe	Within 200' of East-West Railroad
       RRAe	Adjacent to East-West Railroad
	
Condition2: Proximity to various conditions (if more than one is present)
		
       Artery	Adjacent to arterial street
       Feedr	Adjacent to feeder street	
       Norm	Normal	
       RRNn	Within 200' of North-South Railroad
       RRAn	Adjacent to North-South Railroad
       PosN	Near positive off-site feature--park, greenbelt, etc.
       PosA	Adjacent to postive off-site feature
       RRNe	Within 200' of East-West Railroad
       RRAe	Adjacent to East-West Railroad
	
BldgType: Type of dwelling
		
       1Fam	Single-family Detached	
       2FmCon	Two-family Conversion; originally built as one-family dwelling
       Duplx	Duplex
       TwnhsE	Townhouse End Unit
       TwnhsI	Townhouse Inside Unit
	
HouseStyle: Style of dwelling
	
       1Story	One story
       1.5Fin	One and one-half story: 2nd level finished
       1.5Unf	One and one-half story: 2nd level unfinished
       2Story	Two story
       2.5Fin	Two and one-half story: 2nd level finished
       2.5Unf	Two and one-half story: 2nd level unfinished
       SFoyer	Split Foyer
       SLvl	Split Level
	
OverallQual: Rates the overall material and finish of the house

       10	Very Excellent
       9	Excellent
       8	Very Good
       7	Good
       6	Above Average
       5	Average
       4	Below Average
       3	Fair
       2	Poor
       1	Very Poor
	
OverallCond: Rates the overall condition of the house

       10	Very Excellent
       9	Excellent
       8	Very Good
       7	Good
       6	Above Average	
       5	Average
       4	Below Average	
       3	Fair
       2	Poor
       1	Very Poor
		
YearBuilt: Original construction date

YearRemodAdd: Remodel date (same as construction date if no remodeling or additions)

RoofStyle: Type of roof

       Flat	Flat
       Gable	Gable
       Gambrel	Gabrel (Barn)
       Hip	Hip
       Mansard	Mansard
       Shed	Shed
		
RoofMatl: Roof material

       ClyTile	Clay or Tile
       CompShg	Standard (Composite) Shingle
       Membran	Membrane
       Metal	Metal
       Roll	Roll
       Tar&Grv	Gravel & Tar
       WdShake	Wood Shakes
       WdShngl	Wood Shingles
		
Exterior1st: Exterior covering on house

       AsbShng	Asbestos Shingles
       AsphShn	Asphalt Shingles
       BrkComm	Brick Common
       BrkFace	Brick Face
       CBlock	Cinder Block
       CemntBd	Cement Board
       HdBoard	Hard Board
       ImStucc	Imitation Stucco
       MetalSd	Metal Siding
       Other	Other
       Plywood	Plywood
       PreCast	PreCast	
       Stone	Stone
       Stucco	Stucco
       VinylSd	Vinyl Siding
       Wd Sdng	Wood Siding
       WdShing	Wood Shingles
	
Exterior2nd: Exterior covering on house (if more than one material)

       AsbShng	Asbestos Shingles
       AsphShn	Asphalt Shingles
       BrkComm	Brick Common
       BrkFace	Brick Face
       CBlock	Cinder Block
       CemntBd	Cement Board
       HdBoard	Hard Board
       ImStucc	Imitation Stucco
       MetalSd	Metal Siding
       Other	Other
       Plywood	Plywood
       PreCast	PreCast
       Stone	Stone
       Stucco	Stucco
       VinylSd	Vinyl Siding
       Wd Sdng	Wood Siding
       WdShing	Wood Shingles
	
MasVnrType: Masonry veneer type

       BrkCmn	Brick Common
       BrkFace	Brick Face
       CBlock	Cinder Block
       None	None
       Stone	Stone
	
MasVnrArea: Masonry veneer area in square feet

ExterQual: Evaluates the quality of the material on the exterior 
		
       Ex	Excellent
       Gd	Good
       TA	Average/Typical
       Fa	Fair
       Po	Poor
		
ExterCond: Evaluates the present condition of the material on the exterior
		
       Ex	Excellent
       Gd	Good
       TA	Average/Typical
       Fa	Fair
       Po	Poor
		
Foundation: Type of foundation
		
       BrkTil	Brick & Tile
       CBlock	Cinder Block
       PConc	Poured Contrete	
       Slab	Slab
       Stone	Stone
       Wood	Wood
		
BsmtQual: Evaluates the height of the basement

       Ex	Excellent (100+ inches)	
       Gd	Good (90-99 inches)
       TA	Typical (80-89 inches)
       Fa	Fair (70-79 inches)
       Po	Poor (<70 inches
       NA	No Basement
		
BsmtCond: Evaluates the general condition of the basement

       Ex	Excellent
       Gd	Good
       TA	Typical - slight dampness allowed
       Fa	Fair - dampness or some cracking or settling
       Po	Poor - Severe cracking, settling, or wetness
       NA	No Basement
	
BsmtExposure: Refers to walkout or garden level walls

       Gd	Good Exposure
       Av	Average Exposure (split levels or foyers typically score average or above)	
       Mn	Mimimum Exposure
       No	No Exposure
       NA	No Basement
	
BsmtFinType1: Rating of basement finished area

       GLQ	Good Living Quarters
       ALQ	Average Living Quarters
       BLQ	Below Average Living Quarters	
       Rec	Average Rec Room
       LwQ	Low Quality
       Unf	Unfinshed
       NA	No Basement
		
BsmtFinSF1: Type 1 finished square feet

BsmtFinType2: Rating of basement finished area (if multiple types)

       GLQ	Good Living Quarters
       ALQ	Average Living Quarters
       BLQ	Below Average Living Quarters	
       Rec	Average Rec Room
       LwQ	Low Quality
       Unf	Unfinshed
       NA	No Basement

BsmtFinSF2: Type 2 finished square feet

BsmtUnfSF: Unfinished square feet of basement area

TotalBsmtSF: Total square feet of basement area

Heating: Type of heating
		
       Floor	Floor Furnace
       GasA	Gas forced warm air furnace
       GasW	Gas hot water or steam heat
       Grav	Gravity furnace	
       OthW	Hot water or steam heat other than gas
       Wall	Wall furnace
		
HeatingQC: Heating quality and condition

       Ex	Excellent
       Gd	Good
       TA	Average/Typical
       Fa	Fair
       Po	Poor
		
CentralAir: Central air conditioning

       N	No
       Y	Yes
		
Electrical: Electrical system

       SBrkr	Standard Circuit Breakers & Romex
       FuseA	Fuse Box over 60 AMP and all Romex wiring (Average)	
       FuseF	60 AMP Fuse Box and mostly Romex wiring (Fair)
       FuseP	60 AMP Fuse Box and mostly knob & tube wiring (poor)
       Mix	Mixed
		
1stFlrSF: First Floor square feet
 
2ndFlrSF: Second floor square feet

LowQualFinSF: Low quality finished square feet (all floors)

GrLivArea: Above grade (ground) living area square feet

BsmtFullBath: Basement full bathrooms

BsmtHalfBath: Basement half bathrooms

FullBath: Full bathrooms above grade

HalfBath: Half baths above grade

Bedroom: Bedrooms above grade (does NOT include basement bedrooms)

Kitchen: Kitchens above grade

KitchenQual: Kitchen quality

       Ex	Excellent
       Gd	Good
       TA	Typical/Average
       Fa	Fair
       Po	Poor
       	
TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)

Functional: Home functionality (Assume typical unless deductions are warranted)

       Typ	Typical Functionality
       Min1	Minor Deductions 1
       Min2	Minor Deductions 2
       Mod	Moderate Deductions
       Maj1	Major Deductions 1
       Maj2	Major Deductions 2
       Sev	Severely Damaged
       Sal	Salvage only
		
Fireplaces: Number of fireplaces

FireplaceQu: Fireplace quality

       Ex	Excellent - Exceptional Masonry Fireplace
       Gd	Good - Masonry Fireplace in main level
       TA	Average - Prefabricated Fireplace in main living area or Masonry Fireplace in basement
       Fa	Fair - Prefabricated Fireplace in basement
       Po	Poor - Ben Franklin Stove
       NA	No Fireplace
		
GarageType: Garage location
		
       2Types	More than one type of garage
       Attchd	Attached to home
       Basment	Basement Garage
       BuiltIn	Built-In (Garage part of house - typically has room above garage)
       CarPort	Car Port
       Detchd	Detached from home
       NA	No Garage
		
GarageYrBlt: Year garage was built
		
GarageFinish: Interior finish of the garage

       Fin	Finished
       RFn	Rough Finished	
       Unf	Unfinished
       NA	No Garage
		
GarageCars: Size of garage in car capacity

GarageArea: Size of garage in square feet

GarageQual: Garage quality

       Ex	Excellent
       Gd	Good
       TA	Typical/Average
       Fa	Fair
       Po	Poor
       NA	No Garage
		
GarageCond: Garage condition

       Ex	Excellent
       Gd	Good
       TA	Typical/Average
       Fa	Fair
       Po	Poor
       NA	No Garage
		
PavedDrive: Paved driveway

       Y	Paved 
       P	Partial Pavement
       N	Dirt/Gravel
		
WoodDeckSF: Wood deck area in square feet

OpenPorchSF: Open porch area in square feet

EnclosedPorch: Enclosed porch area in square feet

3SsnPorch: Three season porch area in square feet

ScreenPorch: Screen porch area in square feet

PoolArea: Pool area in square feet

PoolQC: Pool quality
		
       Ex	Excellent
       Gd	Good
       TA	Average/Typical
       Fa	Fair
       NA	No Pool
		
Fence: Fence quality
		
       GdPrv	Good Privacy
       MnPrv	Minimum Privacy
       GdWo	Good Wood
       MnWw	Minimum Wood/Wire
       NA	No Fence
	
MiscFeature: Miscellaneous feature not covered in other categories
		
       Elev	Elevator
       Gar2	2nd Garage (if not described in garage section)
       Othr	Other
       Shed	Shed (over 100 SF)
       TenC	Tennis Court
       NA	None
		
MiscVal: $Value of miscellaneous feature

MoSold: Month Sold (MM)

YrSold: Year Sold (YYYY)

SaleType: Type of sale
		
       WD 	Warranty Deed - Conventional
       CWD	Warranty Deed - Cash
       VWD	Warranty Deed - VA Loan
       New	Home just constructed and sold
       COD	Court Officer Deed/Estate
       Con	Contract 15% Down payment regular terms
       ConLw	Contract Low Down payment and low interest
       ConLI	Contract Low Interest
       ConLD	Contract Low Down
       Oth	Other
		
SaleCondition: Condition of sale

       Normal	Normal Sale
       Abnorml	Abnormal Sale -  trade, foreclosure, short sale
       AdjLand	Adjoining Land Purchase
       Alloca	Allocation - two linked properties with separate deeds, typically condo with a garage unit	
       Family	Sale between family members
       Partial	Home was not completed when last assessed (associated with New Homes)
