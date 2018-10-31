Fundraising Churn Analysis-Python

==================================================================================

<h1>Fundraising Churn Analysis</h1>

==================================================================================

<h3>Overview</h3>

The objective of the project is determine which donating customers to an NGO will churn the coming months. Based on this data the NGO can determine the effect on their financials.	

==================================================================================

<h3>Dataset</h3>

The dataset consist of 8 different files which are merged together to obtain the final dataset on which analysis and modeling is done. The dataset used is private hence i am not uploading thee datasets. The details of columns are given below:



| __Metric__     | __Description__                                              |
| -------------- | ------------------------------------------------------------ |
| EXTRELNO       | Unique identifier of each donor                              |
| NAME1TITLE     | Title to address someone                                     |
| POSTCODE       | Postcode                                                     |
| LANGUACODE     | Preferred mailing language                                   |
| EXTRELACTCD    | Activity code of the donor                                   |
| EXTRELSTDT     | Start date of the relationship                               |
| EXTRELDATEN    | End date of the relationship (Missing: not ended)            |
| EXTRELACTDE    | Description of the activity                                  |
| CONTID         | Unique identifier for each contact                           |
| MEDIUMCODE     | Medium of the contact (CI is unknown)                        |
| MNTOPCODE      | Main topic code of the contact                               |
| CLASCODE       | Class of the contact                                         |
| CONTDIREC      | Direction of the communication<br/>I-Incoming<br/>P -Outgoing |
| CONTDATE       | Date of the contact                                          |
| CLASDESC       | Class Description                                            |
| MNTOPDESC      | Main topic Class Description                                 |
| MEDIUMDESC     | Medium Class Description                                     |
| PID            | Unique identifier for each payment                           |
| PDATE          | Date of payment                                              |
| PAMT           | Amount of payment                                            |
| PAYTYPECD      | Paytype<br/>O Bank transfer<br/>D Permanent order<br/>E Own initiative<br/>X Unknown |
| STATUS         | Status of payment<br/>OK Normal/Real payment<br/>CO Correction (internal)<br/>RF RF (Refund)<br/>RC Recall |
| total_donation | Total Donation Amount                                        |

==================================================================================

<h3>Processing</h3>

Initially the data was divided into to time windows Independent window and the Dependent window. Based on the two time windows created the output variable (Churn) was determined. Normal data preprocessing steps of missing value imputation (median , mode)and creating new categories was used. Next Categorical variable were label encoded. The feature postcode was changed to frequency as the feature had high cardinality. Timestamp data were converted to ordinal for analysis purposes. Two models were used to classify, Logistic Regression and Random Forest.

==================================================================================

<h3>Result</h3>

Logistic Regression and Random Forest was used for analysis. From the various metrics we found that Random Forest classifier was better option as Logistic Regressor had overfitted the data by a little. The details of the output from Random Forest Classifier is as follows:

__Confusion Matrix__
[[1017    3]

 [ 6       63]]



| __Metric__              | __Value__                         |
| ----------------------- | --------------------------------- |
| Cross Validation Score  | 99.1729 %   (0.9917296805099172 ) |
| Testing Accuracy        | 99.1735%    (0.9917355371900827)  |
| F1 Score                | 0.9333333333333332                |
| AUC                     | 0.9550511508951407                |
| Average Precision Score | 0.8770511438495628                |

==================================================================================