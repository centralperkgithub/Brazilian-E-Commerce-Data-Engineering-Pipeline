# Brazilian-E-Commerce-Data-Engineering-Pipeline
(Azure Data Factory • ADLS Gen2 • Databricks • PySpark • Synapse • MongoDB)


<hr>

<h2><strong>📌 Agenda</strong></h2>
<ul>
  <li>Understand dataset & business problem</li>
  <li>Ingest multi-source raw data into ADLS Gen2</li>
  <li>Build Medallion Architecture (Bronze → Silver → Gold)</li>
  <li>Transform data at scale using PySpark in Databricks</li>
  <li>Enrich datasets using MongoDB</li>
  <li>Create external tables in Azure Synapse</li>
  <li>Generate insights for analytics dashboards</li>
</ul>

<hr>

<h2><strong>📊 Dataset Details – Olist Brazilian E-Commerce</strong></h2>
<p>
Source: <a href="https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce">Kaggle Dataset Link</a><br><br>
A real Brazilian e-commerce dataset with <strong>100k+ orders</strong> between 2016–2018 from multiple marketplaces.
</p>

<h3><strong>Included Files</strong></h3>
<ul>
  <li>Customers</li>
  <li>Orders</li>
  <li>Order Items</li>
  <li>Payments</li>
  <li>Reviews</li>
  <li>Products</li>
  <li>Sellers</li>
  <li>Geolocation</li>
</ul>

<h3><strong>Dataset Scale</strong></h3>
<ul>
  <li>99,441 customers</li>
  <li>100K+ orders</li>
  <li>30K+ unique products</li>
  <li>1.2M+ geolocation rows</li>
</ul>

<hr>

<h2><strong>🏛️ Architecture</strong></h2>

<img width="3437" height="1842" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/04481dec-37a9-49ce-9962-37ac9f5e4ec7" />


<p align="center">
  <img src="YOUR_IMAGE_PATH_HERE" width="750px">
</p>

<p><strong>Flow:</strong><br>
GitHub (HTTP) + SQL DB + MongoDB → ADF → ADLS Gen2 (Bronze) → Databricks (PySpark) → ADLS (Silver/Gold) → Synapse → Power BI/Tableau
</p>

<hr>

<h2><strong>⚙️ Tech Stack</strong></h2>

<ul>
  <li><strong>Cloud:</strong> Azure, ADLS Gen2</li>
  <li><strong>Ingestion:</strong> Azure Data Factory (HTTP, SQL, param pipelines)</li>
  <li><strong>Processing:</strong> Azure Databricks, PySpark, Delta Lake</li>
  <li><strong>NoSQL:</strong> MongoDB Atlas</li>
  <li><strong>Warehouse:</strong> Azure Synapse Analytics</li>
  <li><strong>Visualization:</strong> Power BI, Tableau</li>
  <li><strong>Version Control:</strong> GitHub</li>
</ul>

<hr>

<h2><strong>🔄 Workflow Overview</strong></h2>

<h3>1️⃣ Bronze Layer – Raw Ingestion</h3>
<ul>
  <li>Ingest raw CSVs from GitHub via ADF HTTP</li>
  <li>Load SQL order/customer tables</li>
  <li>Fetch NoSQL documents from MongoDB</li>
  <li>Store all raw datasets in ADLS Bronze</li>
</ul>

<h3>2️⃣ Silver Layer – Cleaning & Standardization</h3>
<ul>
  <li>Clean timestamps & formats</li>
  <li>Normalize product categories</li>
  <li>Fix missing values and duplicates</li>
  <li>Join orders, customers, items, payments, reviews</li>
</ul>

<h3>3️⃣ Gold Layer – Business Modeling</h3>
<ul>
  <li>Create fact & dimension tables</li>
  <li>Build curated analytical models</li>
  <li>Optimize for reporting & SQL querying</li>
</ul>

<h3>4️⃣ Analytics & BI</h3>
<ul>
  <li>Synapse external tables</li>
  <li>Power BI dashboards (GMV, delivery, customer behavior)</li>
</ul>

<hr>

<h2><strong>🚀 Approach</strong></h2>
<ul>
  <li>Designed Medallion Architecture for scalable processing</li>
  <li>Parameterised ADF pipelines for dynamic ingestion</li>
  <li>Transformed large datasets using PySpark & Delta Lake</li>
  <li>Enriched products & reviews using MongoDB NoSQL collections</li>
  <li>Exposed Gold layer to Synapse for SQL-based analytics</li>
</ul>

<hr>

<h2><strong>📈 Insights Observed (From Notebook Analysis)</strong></h2>

<h3><strong>📍 Customer & Geolocation</strong></h3>
<ul>
  <li><strong>São Paulo, SP</strong> leads in order volume and GMV.</li>
  <li>Significant customer spend variation across cities.</li>
  <li>Large population of low-engagement customers with minimal spending.</li>
</ul>

<h3><strong>🎯 Customer Value Segmentation</strong></h3>
<ul>
  <li><strong>High-value customers contribute 34% of revenue.</strong></li>
  <li>“Champions” & “Potential Loyalists” form the strongest retention segments.</li>
</ul>

<h3><strong>🛒 Product & Category</strong></h3>
<ul>
  <li><strong>Garden Care Tools</strong> dominate both sales volume & revenue.</li>
  <li>Class A: High-value, low-frequency products.</li>
  <li>Class C: Low-value, high-frequency products.</li>
</ul>

<h3><strong>📅 Sales & GMV Trends</strong></h3>
<ul>
  <li>GMV shows steady growth from 2016 to mid-2018.</li>
  <li>Noticeable flattening from late 2018 → market or seasonal slow-down.</li>
  <li>Daily GMV fluctuates with strong seasonality peaks.</li>
</ul>

<h3><strong>⭐ Review Insights</strong></h3>
<ul>
  <li>Ratings 4 and 5 dominate → overall strong customer satisfaction.</li>
  <li>Ratings 1 and 2 highlight issues with delayed delivery or product mismatch.</li>
</ul>

<h3><strong>📦 Order Status</strong></h3>
<ul>
  <li>Delivered orders dominate the dataset.</li>
  <li>Small percentage of canceled/unavailable orders → potential fulfillment gaps.</li>
</ul>

<hr>


