<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>README - Apple iPhone 15 Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        h1, h2, h3 {
            color: #333;
        }
        pre {
            background-color: #f0f0f0;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
        code {
            background-color: #eee;
            padding: 2px 4px;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <h1>Apple iPhone 15 Website</h1>
    
    <h2>Overview</h2>
    <p>This project is a fully responsive website showcasing the Apple iPhone 15. It is built using <strong>React.js</strong> for the frontend framework, <strong>Three.js</strong> for rendering the 3D model, and <strong>GSAP</strong> for animations.</p>
    
    <h2>Features</h2>
    <ul>
        <li>Fully responsive design</li>
        <li>3D model of the iPhone 15</li>
        <li>Smooth animations using GSAP</li>
        <li>Modern and sleek UI</li>
    </ul>
    
    <h2>Technologies Used</h2>
    <ul>
        <li>React.js</li>
        <li>Three.js</li>
        <li>GSAP (GreenSock Animation Platform)</li>
        <li>HTML5</li>
        <li>CSS3</li>
    </ul>
    
    <h2>Installation</h2>
    <p>To run this project locally, follow these steps:</p>
    <ol>
        <li>Clone the repository:
            <pre><code>git clone https://github.com/your-username/iphone15-website.git</code></pre>
        </li>
        <li>Navigate to the project directory:
            <pre><code>cd iphone15-website</code></pre>
        </li>
        <li>Install the dependencies:
            <pre><code>npm install</code></pre>
        </li>
        <li>Start the development server:
            <pre><code>npm start</code></pre>
        </li>
    </ol>
    
    <h2>Usage</h2>
    <p>Once the development server is running, you can view the website in your browser by navigating to <code>http://localhost:3000</code>.</p>
    
    <h2>Project Structure</h2>
    <ul>
        <li><code>public/</code>: Contains static assets like images and the HTML template.</li>
        <li><code>src/</code>: Contains the React components, styles, and 3D model files.
            <ul>
                <li><code>components/</code>: Contains React components for different sections of the website.</li>
                <li><code>styles/</code>: Contains CSS files for styling the components.</li>
                <li><code>models/</code>: Contains 3D model files used by Three.js.</li>
                <li><code>App.js</code>: Main React component where the layout and routing are defined.</li>
                <li><code>index.js</code>: Entry point of the React application.</li>
            </ul>
        </li>
    </ul>
    
    <h2>Example Code</h2>
    
    <h3>HTML (in <code>public/index.html</code>)</h3>
    <pre><code>&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
  &lt;meta charset="UTF-8"&gt;
  &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
  &lt;title&gt;Apple iPhone 15&lt;/title&gt;
  &lt;link rel="stylesheet" href="%PUBLIC_URL%/styles.css"&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;div id="root"&gt;&lt;/div&gt;
&lt;/body&gt;
&lt;/html&gt;
</code></pre>
    
    <h3>CSS (in <code>src/styles/App.css</code>)</h3>
    <pre><code>body, html {
  margin: 0;
  padding: 0;
  font-family: 'Arial, sans-serif';
  background-color: #f5f5f5;
}

.container {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #000;
  color: #fff;
}

.header {
  font-size: 2em;
  margin-bottom: 20px;
}

.model-container {
  width: 100%;
  height: 60vh;
  position: relative;
}

.footer {
  margin-top: 20px;
  font-size: 1em;
  color: #bbb;
}

@media (max-width: 768px) {
  .header {
    font-size: 1.5em;
  }
  
  .model-container {
    height: 50vh;
  }
  
  .footer {
    font-size: 0.8em;
  }
}</code></pre>
    
    <h3>JavaScript (in <code>src/App.js</code>)</h3>
    <pre><code>import React, { useEffect, useRef } from 'react';
import { Canvas } from 'react-three-fiber';
import { gsap } from 'gsap';
import { OrbitControls } from '@react-three/drei';
import iPhoneModel from './models/iPhoneModel';
import './styles/App.css';

function App() {
  const containerRef = useRef(null);

  useEffect(() => {
    gsap.from(containerRef.current, { opacity: 0, duration: 1 });
  }, []);

  return (
    <div className="container" ref={containerRef}>
      <header className="header">
        Apple iPhone 15
      </header>
      <div className="model-container">
        <Canvas>
          <ambientLight intensity={0.5} />
          <directionalLight position={[0, 5, 5]} />
          <iPhoneModel />
          <OrbitControls />
        </Canvas>
      </div>
      <footer className="footer">
        © 2024 Apple Inc.
      </footer>
    </div>
  );
}

export default App;
</code></pre>
    
    <h3>JavaScript (in <code>src/models/iPhoneModel.js</code>)</h3>
    <pre><code>import React, { useRef } from 'react';
import { useLoader } from 'react-three-fiber';
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader';

const iPhoneModel = () => {
  const model = useLoader(GLTFLoader, '/path/to/iphone15-model.glb');
  return <primitive object={model.scene} scale={[0.5, 0.5, 0.5]} />;
};

export default iPhoneModel;
</code></pre>
    
    <h2>Contributing</h2>
    <p>If you would like to contribute to this project, please fork the repository and create a pull request. We welcome all contributions!</p>
    
    <h2>License</h2>
    <p>This project is licensed under the MIT License. See the LICENSE file for details.</p>
</body>
</html>
