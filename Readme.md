<html>
<body>
<h1><b>YOLO Application</b></h1>
<p><b>Yolo</b> is an e-commerce platform.</p>
<p>This project deploys an application (e-commerce 'YOLO') using Kubernetes orchestration concepts on Google Kubernetes Engine (GKE)</p>
<h2><b>Features</b></h2>
<ul>
  <li>Upload images for object detection</li>
  <li>Perform object detection using the YOLO algorithm</li>
  <li>View the detected objects in the uploaded images</li>
</ul>
<h2><b>Technologies Used</b></h2>
<ul>
  <li>Frontend: React.js</li>
  <li>Backend: Node.js, Express.js</li>
  <li>Object Detection: YOLO algorithm</li>
  <li>Containerization: Docker</li>
  <li>Orchestration: Kubernetes</li>
  <li>Declarative files: YAML</li>
</ul>
<h2><b>Installation</b></h2>
<ol>
  <li>Install minikube on your machine.</li>
  <li>Clone the repository provided on the IP. (git clone https://github.com/your-username/yolo-app.git)</li>
  <li>Install all dependencies needed.</li>
  <li>Build the Docker images, ensure your containers are building independently.</li>
  <li>Start the application.</li>
  <li>Create the deployment, service, config, and PVC YAML files.</li>
  <li>Deploy on GKE and access the external IP from the services.</li>
</ol>
<h2><b>Configuration</b></h2>
<p>The following environment variables can be configured for the backend:</p>
<ul>
  <li>MONGODB_URI: The URI for connecting to the MongoDB database.</li>
  <li>NODE_ENV: The environment mode (e.g., development, production).</li>
</ul>
<p>Create a .env file in the backend directory and set the values for the above variables:</p>
<pre><code>MONGODB_URI=mongodb://localhost:27017/yolo-app
NODE_ENV=development
</code></pre>
<h2><b>Usage</b></h2>
<p>Access the web application in your browser at <a href="http://localhost:3000">http://localhost:3000</a>.</p>
<p>Access the database in your browser at <a href="http://localhost:5000">http://localhost:5000</a>.</p>
<p>You can try to add an item for object detection.</p>
<p>MongoDB Atlas used as the backend database. You can use your connection string to test the same.</p>
<h2><b>License</b></h2>
<p>License MIT License: Copyright (c) 2023</p>
<h2><b>Acknowledgements</b></h2>
<ul>
  <li>YOLO algorithm implementation: yolo</li>
  <li>React.js: React</li>
  <li>Node.js: Node.js</li>
  <li>Express.js: Express.js</li>
  <li>Docker: Docker</li>
  <li>Kubernetes: Kubernetes</li>
  <li>YAML</li>
</ul>
</body>
</html>




