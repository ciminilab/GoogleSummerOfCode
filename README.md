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

| Project idea | Expected Outcomes | Expected Project Size | Skills Required / Preferred | Mentors | GitHub link(s) | Description |
---------------|-------------------|-----------------------|---------------------------|---------|----------------|-------------|
| Harmonize and simplify CellProfiler's export functionality | New CellProfiler modules ExportMeasurements and ExportCPAProjectFiles; CSV, MySQL, and SQlite backends for the Export module | Large | Python, SQL | [@bethac07](https://github.com/bethac07), [@gnodar01](https://github.com/gnodar01) | [here](https://github.com/CellProfiler/CellProfiler/discussions/4714) | CellProfiler has two modules for exporting measurements: ExportToDatabase (which can write to MySQL or SQLite) and ExportToSpreadsheet (which creates CSVs). Over the years, the functionalities of these two modules has diverged in often-surprising ways; for example, one can select which measurements to export only in EtS, not EtD. We would like to create a single, extensible ExportMeasurements module with a single set of UI choices, which then calls out to backends which do the actual writing. This will allow more consistent user behavior, as well as allow us to more easily support other kinds of output files (such as Parquet) in the future. |
| Implement "soft warnings" in CellProfiler | A new warning class in CellProfiler, with specific behavior warnings implemented in many modules | Large | Python | [@bethac07](https://github.com/bethac07), [@ErinWeisbart](https://github.com/ErinWeisbart), [@gnodar01](https://github.com/gnodar01) | [here](https://github.com/CellProfiler/CellProfiler/issues/4961) | CellProfiler's flexibility comes with a downside; there are many things a user CAN do that are not often a good idea TO DO, and for an inexperienced user, it is sometimes hard to know what is suboptimal (or why). We have begun internally collecting cases where we would like a new "soft warning" class to be implemented; in this project, the applicant will make changes to the CellProfiler internals to enable such a warning class, and implement the existing cases |

### Piximi {#piximi}

[Piximi](https://piximi.app/) is an open-source image analysis client-side web-app written in TypeScript. It is an "Images to Discovery" platform that allows users to upload images, segment and/or classify them with deep learning, and then measure them all without installation or the data needing to leave their machine.

| Project idea | Expected Outcomes | Expected Project Size | Skills Required / Preferred | Mentors | GitHub link(s) | Description |
---------------|-------------------|-----------------------|---------------------------|---------|----------------|-------------|
| a | b | c | d | e | f | g |

### Bilayers {#bilayers}

[Bilayers](https://bilayers.org/) is an open-source image analysis specification and CI/CD, which involves containerization, a LinkML-based specifiation, and Jinja templating. It is designed to allow bioimage analysts to describe any containerized tool or algorithm in a human-readable config file, and to use that config file to automatically create GUI tool versions as well as interfaces to other tools (such as CellProfiler).

| Project idea | Expected Outcomes | Expected Project Size | Skills Required / Preferred | Mentors | GitHub link(s) | Description |
---------------|-------------------|-----------------------|---------------------------|---------|----------------|-------------|
| Expand our wrapper list | You create one or more interfaces for the Bilayers CI/CD | Small (1-2 interfaces) through Medium (3-5 interfaces) | Docker, CI/CD, Jinja templating, LinkML | [@bethac07](https://github.com/bethac07), [@gnodar01](https://github.com/gnodar01) | [here](https://github.com/orgs/bilayer-containers/discussions/4) | Bilayers is a system of wrapped tools and interface wrappers that encapsulate them. We have a list of planned wrappers, but are happy to consider other GUI tools and/or interfaces to other workflow tools if they hit a gap in our current ecosystem. Please tell us more in your proposal! |
| Expand our wrapped tool list | You create one or more containers for image analysis tools or algorithms, and/or fill out config files and test interfaces for several existing containers | Small (4-5 tools) through Medium (10-20 tools) | Docker, CI/CD, LinkML | [@bethac07](https://github.com/bethac07) | [here](https://github.com/orgs/bilayer-containers/discussions/3) | Bilayers is a system of wrapped tools and interface wrappers that encapsulate them. The bioimage analysis landscape has new tools seemingly coming out every day, most of which are not containerized, and many of which are not user friendly (and/or are only accessilbe in one interface). We have a small list of tools we like, but we're open to many other tools if they hit a gap in our current ecosystem. Please tell us more in your proposal! |
| Create a better interface for filling out config files | One or two small, maintainable tools and/or widgets for creating filled config files | Small through Medium | Docker, CI/CD, LinkML | [@bethac07](https://github.com/bethac07) | n/a | While the Bilayers config file is smaller and much friendlier than some other large specifications like CWL or WDL, the easier we make it to fill out and/or submit config files, the more config files the project will accumulate. We envision something like a Streamlit app or a Marimo notebook, but are open to even more creative solutions - please tell us more in your proposal! |
