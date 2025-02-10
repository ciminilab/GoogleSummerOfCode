# Google Summer of Code Projects in the [Cimini Lab](https://cimini-lab.broadinstitute.org/) at the [Broad Institute Imaging Platform](https://www.broadinstitute.org/imaging)

The Broad Institute Imaging Platform (est 2007) is a group of computational biologists and computationalists who work to create methods, software, and workflows designed to turn light microscopy images into answered questions. The Cimini lab (est 2021) creates and maintains a number of open-source software tools for those purposes. Read more about what we do at our lab website (linked above) or our ["stuff we make" site](https://ciminilab.github.io/WeMakeStuff/).

Below are the projects we are hoping may be of some interest for GSoC 2025 hopeful-contributors! Feel free to reach out to bcimini AT broadinstitute DOT org if you want to propose something in one of our projects not listed below (or even better, hop into the Issues and/or Discussions for the project!)

Jump to:

[How to apply](#apply) | [CellProfiler projects](#cellprofiler) | [Piximi projects](#piximi) | [Bilayers projects](#bilayers)

## How to apply {#apply}

- Please prepare a description of
  - What you would like to work on
  - What you see as the major opportunities and challenges
  - Please break the project down into 3-6 milestones, and prepare a timeline for finishing each (in terms of both "hours of work" and "calendar time"
- Please include a resume or CV, as well as 2-3 paragraphs describing your overall career interests (if known), why this work would suit you, and what you would aim to learn. If you have a history of working on other codebases (especially collaborative projects), please do highlight this.
- Preference will be given to applicants who have already participated in at least one issue and/or discussion; especial preference will be given to applicants who have made a PR (PRs need not be large, but they should be thoughtful).

## Projects we are looking for help with

### CellProfiler {#cellprofiler}

[CellProfiler](https://cellprofiler.org/) is an open-source image analysis workflow tool written in Python. It allows users to assemble no-code workflow pipelines to apply to however many images they have, whether that is 100 or 1,000,000.

<table class="project-table">
  <thead>
    <tr>
      <th>Project idea</th>
      <th>Expected Outcomes</th>
      <th>Expected Project Size</th>
      <th>Skills Required / Preferred</th>
      <th>Mentors</th>
      <th>GitHub link(s)</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Harmonize and simplify CellProfiler’s export functionality</td>
      <td><div class="long-description">New CellProfiler modules <code>ExportMeasurements</code> and <code>ExportCPAProjectFiles</code>; CSV, MySQL, and SQlite backends for the Export module</div></td>
      <td>Large</td>
      <td>Python, SQL</td>
      <td><a href="https://github.com/bethac07">@bethac07</a>, <a href="https://github.com/gnodar01">@gnodar01</a></td>
      <td><a href="https://github.com/CellProfiler/CellProfiler/discussions/4714">here</a></td>
      <td><div class="long-description">CellProfiler has two modules for exporting measurements: <ul><li><code>ExportToDatabase</code> (which can write to MySQL or SQLite)</li> <li><code>ExportToSpreadsheet</code> (which creates CSVs)</li></ul> Over the years, the functionalities of these two modules has diverged in often-surprising ways; for example, one can select which measurements to export only in EtS, not EtD. <br/><br/>We would like to create a single, extensible <code>ExportMeasurements</code> module with a single set of UI choices, which then calls out to backends which do the actual writing. This will allow more consistent user behavior, as well as allow us to more easily support other kinds of output files (such as Parquet) in the future.</div></td>
    </tr>
    <tr>
      <td>Implement “soft warnings” in CellProfiler</td>
      <td><div class="long-description">A new warning class in CellProfiler, with specific behavior warnings implemented in many modules</div></td>
      <td>Large</td>
      <td>Python</td>
      <td><a href="https://github.com/bethac07">@bethac07</a>, <a href="https://github.com/ErinWeisbart">@ErinWeisbart</a>, <a href="https://github.com/gnodar01">@gnodar01</a></td>
      <td><a href="https://github.com/CellProfiler/CellProfiler/issues/4961">here</a></td>
      <td><div class="long-description">CellProfiler’s flexibility comes with a downside; there are many things a user <strong>CAN</strong> do that are not often a good idea <strong>TO DO</strong>, and for an inexperienced user, it is sometimes hard to know what is suboptimal (or why). <br/><br/>We have begun internally collecting cases where we would like a new “soft warning” class to be implemented; in this project, the applicant will make changes to the CellProfiler internals to enable such a warning class, and implement the existing cases</div></td>
    </tr>
  </tbody>
</table>

### Piximi {#piximi}

[Piximi](https://piximi.app/) is an open-source image analysis client-side web-app written in TypeScript. It is an "Images to Discovery" platform that allows users to upload images, segment and/or classify them with deep learning, and then measure them all without installation or the data needing to leave their machine.

<table class="project-table">
  <thead>
    <tr>
      <th>Project idea</th>
      <th>Expected Outcomes</th>
      <th>Expected Project Size</th>
      <th>Skills Required / Preferred</th>
      <th>Mentors</th>
      <th>GitHub link(s)</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Expanding Testing Infrastructure for Piximi</td>
      <td><div class="long-description" >By the end of the project, Piximi will have a robust, automated testing suite that improves software reliability, simplifies debugging, and enhances the contributor experience. The project will leave behind well-documented test cases and a structured approach to testing, making future development smoother.</div></td>
      <td>Large</td>
      <td>
      <ul>
      <li> Required:
      <ul>
      <li>
      JavaScript/TypeScript
      </li>
      <li>
      React
      </li>
        </ul>
        </li>
        <li> Preferred/Want to Learn:
        <ul>
        <li>Build Tools (Vite)</li>
        <li> Testing Frameworks (Vitest, etc.)</li>
        <li>CI/CD Concepts</li>
        </ul>
        </li>
      </ul>
      </td>
      <td><a href="https://github.com/Andrea-Papaleo">@Andrea-Papaleo</a></td>
      <td><a href="https://github.com/piximi/piximi/discussions/657">GitHub</a></td>
      <td><div class="long-description" ><div>While Piximi's core functionality is growing, the testing infrastructure remains limited, with only a small number of utility functions covered by Vitest.</div>
      <br/>
      
<div>
This project aims to significantly expand Piximi’s testing coverage by implementing:
<ul>
<li>Comprehensive unit tests using Vitest to ensure core functions work reliably.</li>
<li>End-to-end (E2E) tests to verify user workflows and prevent regressions.</li>
<li>Component-based tests using Storybook to improve UI reliability and usability.</li>
<li>User stories and test documentation, making future contributions easier and more predictable.</li>
</ul>
</div>
<div>
By enhancing the test suite, this project will improve developer confidence, stability, and maintainability, ensuring Piximi remains a robust and user-friendly tool.
</div>
</div>
</td>

</tr>
<tr>
<td>Implementing a YOLACT-Style Model for Real-Time Instance Segmentation in Piximi</td>
<td><div class="long-description" >Piximi will feature an integrated, YOLACT-style instance segmentation model capable of running entirely in the browser, giving users a fast, secure, and open-source alternative to existing bioimage analysis tools.</div></td>
<td>Large</td>
<td>
<ul>
<li>
Required:
<ul>
<li>JavaScript/Typescript</li>
<li>Deep Learning Frameworks</li>
</ul>
</li>
<li>Preferred/Want to Learn:
<ul>
<li>Model Optimization Techniques</li>
<li>Computer Vision & Image Processing</li>
</ul>
</li>
</ul>
</td>
<td>
<a href="https://github.com/Andrea-Papaleo">@Andrea-Papaleo</a>
</td>
<td>N/A</td>
<td><div class="long-description">One of the core functionalities Piximi aims to enhance is real-time instance segmentation for biological objects (e.g., cells, bacteria, or tissues).
<br/>
<br/>
<div>
This project will focus on:
<ul>
<li>Developing and fine-tuning a YOLACT-style model (You Only Look At Coefficients) for biological image segmentation.</li>
<li>Pretraining the model using high-quality biological datasets to ensure accurate and robust segmentation results.</li>
<li>Optimizing and porting the model to JavaScript, enabling fast, client-side inference in Piximi without requiring a backend server.</li>
</ul>

This will allow seamless, on-device segmentation, ensuring privacy, speed, and accessibility for users analyzing bioimages.

</div>
</div>
</td>

</tr>
<tr>
<td>Building an API for AnyWidget to Interface with Piximi in Jupyter Notebooks</td>
<td><div class="long-description">Jupyter notebook users will be able to directly interact with Piximi, running image analysis tasks within an interactive Python environment. This will provide greater flexibility and scripting capabilities for researchers using Piximi in bioimage workflows.</div></td>
<td>Large</td>
<td>
<ul>
<li> Required:
<ul>
<li>JavaScript/TypeScript</li>
<li>Python & Jupyter Notebook</li>
</ul>
</li>
<li> Preferred/Want to Learn:
<ul>
<li>AnyWidget or Widget Frameworks</li>
<li>REST/WebSockets</li>
</ul>
</li>
</ul>
</td>
<td><a href="https://github.com/Andrea-Papaleo">@Andrea-Papaleo</a></td>
<td>N/A</td>
<td><div class="long-description">While Piximi provides an intuitive browser-based interface, many researchers and data scientists prefer working within Jupyter notebooks for interactive data exploration and analysis.
<br/>
<div>
This project will enable Piximi’s functionality within Jupyter notebooks by:
<ul>
<li>Building an API for use with AnyWidget, allowing Jupyter users to access Piximi’s tools.</li>
<li>Connecting Piximi’s Redux state to the API, ensuring seamless interaction between the Jupyter frontend and Piximi’s image-processing capabilities.</li>
<li>Providing a smooth user experience, enabling users to upload images, annotate, classify, and measure them—all from a Jupyter notebook.</li>
</ul>
</div>

This integration will expand Piximi’s accessibility and make it easier for researchers to incorporate Piximi into their Python-based workflows.</div>

</td>
</tr>

  </tbody>
</table>

### Bilayers {#bilayers}

[Bilayers](https://bilayers.org/) is an open-source image analysis specification and CI/CD, which involves containerization, a LinkML-based specifiation, and Jinja templating. It is designed to allow bioimage analysts to describe any containerized tool or algorithm in a human-readable config file, and to use that config file to automatically create GUI tool versions as well as interfaces to other tools (such as CellProfiler).

<table class="project-table">
  <thead>
    <tr>
      <th>Project idea</th>
      <th>Expected Outcomes</th>
      <th>Expected Project Size</th>
      <th>Skills Required / Preferred</th>
      <th>Mentors</th>
      <th>GitHub link(s)</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Expand our wrapper list</td>
      <td><div class="long-description">You create one or more interfaces for the Bilayers CI/CD</div></td>
      <td>Small (1-2 interfaces) through Medium (3-5 interfaces)</td>
      <td>Docker, CI/CD, Jinja templating, LinkML</td>
      <td><a href="https://github.com/bethac07">@bethac07</a>, <a href="https://github.com/gnodar01">@gnodar01</a></td>
      <td><a href="https://github.com/orgs/bilayer-containers/discussions/4">here</a></td>
      <td><div class="long-description">Bilayers is a system of wrapped tools and interface wrappers that encapsulate them. We have a list of planned wrappers, but are happy to consider other GUI tools and/or interfaces to other workflow tools if they hit a gap in our current ecosystem. Please tell us more in your proposal!</div></td>
    </tr>
    <tr>
      <td>Expand our wrapped tool list</td>
      <td><div class="long-description">You create one or more containers for image analysis tools or algorithms, and/or fill out config files and test interfaces for several existing containers</div></td>
      <td>Small (4-5 tools) through Medium (10-20 tools)</td>
      <td>Docker, CI/CD, LinkML</td>
      <td><a href="https://github.com/bethac07">@bethac07</a></td>
      <td><a href="https://github.com/orgs/bilayer-containers/discussions/3">here</a></td>
      <td><div class="long-description">Bilayers is a system of wrapped tools and interface wrappers that encapsulate them. The bioimage analysis landscape has new tools seemingly coming out every day, most of which are not containerized, and many of which are not user friendly (and/or are only accessilbe in one interface). We have a small list of tools we like, but we’re open to many other tools if they hit a gap in our current ecosystem. Please tell us more in your proposal!</div></td>
    </tr>
    <tr>
      <td>Create a better interface for filling out config files</td>
      <td><div class="long-description">One or two small, maintainable tools and/or widgets for creating filled config files</div></td>
      <td>Small through Medium</td>
      <td>Docker, CI/CD, LinkML</td>
      <td><a href="https://github.com/bethac07">@bethac07</a></td>
      <td>n/a</td>
      <td><div class="long-description">While the Bilayers config file is smaller and much friendlier than some other large specifications like CWL or WDL, the easier we make it to fill out and/or submit config files, the more config files the project will accumulate. We envision something like a Streamlit app or a Marimo notebook, but are open to even more creative solutions - please tell us more in your proposal!</div></td>
    </tr>
  </tbody>
</table>
