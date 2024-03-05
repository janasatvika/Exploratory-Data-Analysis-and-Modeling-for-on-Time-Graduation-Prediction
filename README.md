# On-Time Graduation Prediction: Data Analytics (EDA) and Machine Learning Approaches
![Logo](https://github.com/janasatvika/On-Time-Graduation-Prediction/blob/main/img%20assets/graduation.jpg)

<!-- Introduction -->
## <span style="font-size: 100px">&#128073;</span> <b>Introduction</b>

<p>
  Investigating the phenomenon of students graduating on time was not only an
  intriguing topic but also a crucial parameter that reflected the quality and
  success of a university and its programs. Therefore, a comprehensive and
  measurable strategy was necessary to overcome this challenge. In this context,
  an Exploratory Data Analysis (EDA) focused on the Informatics Engineering
  Education or Pendidikan Teknik Informatika (PTI) Program was conducted. The
  objective was to comprehensively analyze student graduation data, identifying
  patterns and trends, and examining the relationships between variables to
  understand the factors that influenced timely graduation. Additionally, the
  Decision Tree algorithm was implemented in a predictive modeling effort to
  produce accurate predictions regarding the likelihood of students graduating
  on time. This analysis aimed to provide valuable insights for decision makers
  in designing effective strategies that supported on-time student graduation
  and improved education quality standards.
</p>

<!-- Method -->
## <span style="font-size: 100px">&#128073;</span> <b>Method</b>

<p>
  The process of exploratory data analysis (EDA) involves several crucial steps,
  including data identification, univariate analysis, bivariate analysis, and
  multivariate analysis. Once the available data has undergone a series of
  in-depth analyses, the next step is to apply important pre-processing
  techniques such as feature encoding and data normalization. These techniques
  aim to ensure that the data used in constructing the prediction model is in an
  optimal state. These processes produce final data that is ready to be used in
  designing the prediction model. In this case, the Decision Tree algorithm
  serves as the basis for the prediction model. To ensure that the resulting
  model is optimal and accurate, the Hyperparameter tuning technique is applied
  using GridSearchCV. This technique enables the exploration of various
  combinations of Decision Tree parameters, maximizing the resulting
  classification results for reliability.
</p>

<!-- Table -->
### <span style="font-size: 100px">&#128204;</span> Graduation dataset

<p>
  The dataset used comprises graduation data for PTI program students from
  2014-2017, totaling 455 rows of data.
</p>

<table>
  <tr>
    <th><b>Features</b></th>
    <th><b>Data type</b></th>
    <th><b>Description</b></th>
  </tr>
  <tr>
    <td>
      <span style="font-size: 100px">&#128273;</span>
      Student ID
    </td>
    <td>object</td>
    <td>Unique student id</td>
  </tr>
  <tr>
    <td>Gender</td>
    <td>object</td>
    <td>Student gender</td>
  </tr>
  <tr>
    <td>SHS type</td>
    <td>object</td>
    <td>Previous Student's Educational Background</td>
  </tr>
  <tr>
    <td>UKT</td>
    <td>int64</td>
    <td>
      Tuition fees are required to be paid by students every semester. The fees
      are adjusted based on the economic ability of the parents.
    </td>
  </tr>
  <tr>
    <td>Parents' income</td>
    <td>int64</td>
    <td>Monthly income received from parents</td>
  </tr>
  <tr>
    <td>IPS 1</td>
    <td>float64</td>
    <td>Grade Point Average in the 1st semester</td>
  </tr>
  <tr>
    <td>IPS 2</td>
    <td>float64</td>
    <td>Grade Point Average in the 2nd semester</td>
  </tr>

  <tr>
    <td>IPS 3</td>
    <td>float64</td>
    <td>Grade Point Average in the 3rd semester</td>
  </tr>
  <tr>
    <td>IPS 4</td>
    <td>float64</td>
    <td>Grade Point Average in the 4th semester</td>
  </tr>
  <tr>
    <td>Retake total</td>
    <td>int64</td>
    <td>Grades are repeated in the first four semesters</td>
  </tr>
  <tr>
    <td>
      <span style="font-size: 100px">&#11088;</span>
      Graduation status
    </td>
    <td>object</td>
    <td>Dependent attribute or data class, (values: <b>on-Time</b> and <b>Late</b>)</td>
  </tr>
</table>

<!-- Results and Method -->
## <span style="font-size: 100px">&#128073;</span> <b>Results & Discussion</b>

### <span style="font-size: 100px">&#128161;</span> EDA insights
<ul>
  <li>
    The high percentage of students unable to complete their studies on time
    suggests significant challenges within the study program that require
    immediate attention.
  </li>
  <li>
    The majority of students in the PTI program from 2014-2017 graduated from
    SMA, followed by those from SMK, and the fewest from MA. This pattern
    indicates that most PTI students have a high school educational background,
    while a significant number come from SMK.
  </li>
  <li>
    During the first four semesters, a student may repeat a class a maximum of
    two times.
  </li>
  <li>
    The proportion of female students who complete their studies on time is
    higher than that of male students.
  </li>
  <li>
    Students who can graduate on time have an average IPS above 3.30.
    Meanwhile, students who do not manage to graduate on time tend to have an
    average IPS below 3.00, with a tendency for the average IPS to decrease over
    time.
  </li>
  <li>
    Students with a vocational background were found to have a higher number of
    students who completed their studies on time in the PTI program.
  </li>
  <li>
    There is a correlation between repeating classes and a delay in graduating
    on time. This suggests that repeating classes may hinder timely completion
    of studies.
  </li>
  <li>
    Many students who maintain an average IPS above 3.00 for four consecutive
    semesters can graduate on time. It should be noted, however, that
    maintaining an average IPS above 3.00 does not guarantee that students will
    be able to graduate on time.
  </li>
</ul>

### <span style="font-size: 100px">&#128161;</span> Modeling process insights
<ul>
  <li>
    Best Hyperparameters of Decision Tree Model: (criterion= <b>entropy</b>,
    max_depth= <b>5</b>, max_leaf_nodes= <b>9</b>, min_samples_split= <b>6</b>)
  </li>
  <li>
    <b>Confusin matrix table</b>
    <table>
      <tr>
        <td></td>
        <td><b>Predicted 0</b></td>
        <td><b>Predicted 1</b></td>
      </tr>
      <tr>
        <td><b>Actual 0</b></td>
        <td>80</td>
        <td>4</td>
      </tr>
      <tr>
        <td><b>Actual 1</b></td>
        <td>5</td>
        <td>2</td>
      </tr>
    </table>
  </li>
  <li>
    Performance score: (Accuracy score= <b>90.11%</b>, Recall score=
    <b>28.57%</b>, Precision score= <b>33.33%</b>, dan f1-score= <b>30.77%</b>)
  </li>
</ul>

<!-- Results and Method -->
## <span style="font-size: 100px">&#128073;</span> <b>Conclusion</b>

<p>
  While the model's accuracy score is high, the precision, recall, and f1-scores
  remain low. The low recall score suggests that the model is better at
  predicting data with the Late class, but less effective in predicting the
  On-Time class. This is due to the unbalanced distribution between the Late and
  On-Time classes in the training data, which is a crucial problem that requires
  careful handling. To address this issue, a comprehensive approach is required.
  One effective method is the Imbalance dataset handling technique, which
  balances the training data to improve the model's ability to learn from both
  existing classes. Additionally, testing is conducted to evaluate the impact of
  this technique on the overall performance of the model. Thus, the model is
  expected to provide more accurate and reliable predictions for both Late and
  On-Time classes.
</p>

<!-- References -->
## <b>References:</b>
<ul>
  <li>-</li>
</ul>

