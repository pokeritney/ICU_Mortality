---


---

<h1 id="bdhteam48project">BDHteam48project</h1>
<h1 id="files">Files</h1>
<ul>
<li>
<p>The workspace synchronization will sync all your files, folders and settings automatically. This will allow you to fetch your workspace on any other device.</p>
<blockquote>
<p>To start syncing your workspace, just sign in with Google in the menu.</p>
</blockquote>
</li>
<li>
<p>The file synchronization will keep one file of the workspace synced with one or multiple files in <strong>Google Drive</strong>, <strong>Dropbox</strong> or <strong>GitHub</strong>.</p>
<blockquote>
<p>Before starting to sync files, you must link an account in the <strong>Synchronize</strong> sub-menu.</p>
</blockquote>
</li>
</ul>
<h1 id="publication">Publication</h1>
<p>Publishing in StackEdit makes it simple for you to publish online your files. Once you’re happy with a file, you can publish it to different hosting platforms like <strong>Blogger</strong>, <strong>Dropbox</strong>, <strong>Gist</strong>, <strong>GitHub</strong>, <strong>Google Drive</strong>, <strong>WordPress</strong> and <strong>Zendesk</strong>. With <a href="http://handlebarsjs.com/">Handlebars templates</a>, you have full control over what you export.</p>
<blockquote>
<p>Before starting to publish, you must link an account in the <strong>Publish</strong> sub-menu.</p>
</blockquote>
<h2 id="publish-a-file">Publish a File</h2>
<p>You can publish your file by opening the <strong>Publish</strong> sub-menu and by clicking <strong>Publish to</strong>. For some locations, you can choose between the following formats:</p>
<ul>
<li>Markdown: publish the Markdown text on a website that can interpret it (<strong>GitHub</strong> for instance),</li>
<li>HTML: publish the file converted to HTML via a Handlebars template (on a blog for example).</li>
</ul>
<h2 id="data-pre-processing">Data Pre-Processing</h2>
<p><strong>All files related to data pre-processing are under Data folder.</strong></p>
<p>The initial exploratory data analysis are saved under Data/EDA.ipynb.</p>
<h3 id="queries---bigquery">Queries - BigQuery</h3>
<p>Below describes the purpose of each query of extracting our features. The feature engineering process was inspired by <a href="https://github.com/alistairewj/mortality-prediction/tree/master/queries">Alistair Johnson</a> 's morality prediction project. We used some of his queries for reference when building our own features. The data was extracted for 6hrs, 12hrs, 24hrs and 48hrs during a patient’s ICU stay.</p>

<table>
<thead>
<tr>
<th>Queries</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>combined_data_process.sql</td>
<td>Our combined feature engineering queries</td>
</tr>
<tr>
<td>combined_data_lstm.sql</td>
<td>Our combined feature engineering queries exclude categorical variables</td>
</tr>
<tr>
<td>bg.sql</td>
<td>Extract blood gases and chemistry values which were found in LABEVENTS</td>
</tr>
<tr>
<td>bg_art.sql</td>
<td>Extract blood gases and chemistry values which were found in CHAREVENTS</td>
</tr>
<tr>
<td>cohort.sql</td>
<td>Generate each ICU stay’s information</td>
</tr>
<tr>
<td>data.sql</td>
<td>combines all views to get all features at all time points</td>
</tr>
<tr>
<td>gcs.sql</td>
<td>Get Glasgow Coma Scale (GCS) from the cohort view</td>
</tr>
<tr>
<td>lab.sql</td>
<td>Get laboratory results from LABEVENTS</td>
</tr>
<tr>
<td>uo.sql</td>
<td>Get urine outputs from OUTPUTEVENTS</td>
</tr>
<tr>
<td>vital.sql</td>
<td>Vital signs for the first 24 hours of a patient’s stay from CHAREVENTS</td>
</tr>
<tr>
<td>cohort_hour.sql</td>
<td>extracts the cohort and every possible hour they were in the ICU</td>
</tr>
</tbody>
</table><p>All queries are processed on Google BigQuery with MIMIC-III integrated cloud database. Here are the interface:</p>
<p>![BQ](big query.png)</p>
<h3 id="data-files">Data Files</h3>
<p>All the pre-processed data files are exported into csv format and saved under Data/Output.zip. Since GitHub does not allow file upload more than 100MB, please unzip if necessary.</p>

