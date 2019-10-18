# Glossary for the OSS Tooling Landscape

## Company External

### Source Code Repository
Systems or services that provide source code. This is typically (also) a version control system. The compliance tooling obtains the source code of 3rd party dependencies, i.e., FOSS components from such repositories.
Examples: [Software Heritage](https://www.softwareheritage.org/)

### Artifact Repository
Systems or services that provides (binary) software artifacts and metadata stored in a defined directory structure which is used to retrieve artifacts during a build process. Software artifacts may be of type proprietary, commercial, FOSS. The Artifact repository may also be used to store the source code of FOSS components besides the binary artifact for usage within the compliance process, e.g., for starting a license scan or creating the source code bundle to be delivered with the product.
Examples: [Maven central](https://mvnrepository.com/repos/central), [npm](https://www.npmjs.com/), [PyPI](https://pypi.org/)

### Security Vulnerability Database
Systems or services that provide information about publicly known security vulnerabilities of software artefacts.
Example: [NVD](https://nvd.nist.gov/)

### License Obligations Database
Systems or services that provide Data about obligations and prohibitions of (FOSS) licenses.

### Public License Master Database
Publicly available information about Open Source licenses (e.g. commonly accepted license identifiers).

### FOSS Metadata Database
Systems or services that provide descriptive data of software artefacts (mainly FOSS). Data could be: the declared license for a component, the source location (e.g., Git commit) for a version, details to be included in attributions (e.g., copyright holders in a Notices file), etc.
Example: [ClearlyDefined](https://clearlydefined.io/)

## Company Internal

### Artifact Repository
A system or service providing (binary) software artifacts and metadata stored in a defined directory structure which is used to retrieve artifacts during a build process. This is used as a cache for the external Artifact Repository to ensure the availability of all components used within the company, it is also the storage for the build software artifacts of the company, used in the Continuous Integration Infrastructure to store the build results.
Example: [Archiva](https://archiva.apache.org/index.cgi)

### Black-/Whitelist
In some cases it may make sense to provide a list of accetable (white) or not acceptable (black) licenses or components. Thus a developer aiming to use a new component may verify against this list whether his aim will violate any company/project rules. In particular critical components even a "whitelisting requirement" could be issued, so a competent sponsor may ensure that only allowed components will be applied. Modern tooling should support automated verification of such lists or a whitelist enforcement. 

### Build Tool
A system that builds a software project and creates the binaries and executables for the software. During this process, the build technology has a technology dependent way to identify and provide dependencies needed to build and run the software. This information is used to run the compliance check on the project.

### Compliance Checker
A set of systems or services that are executed on the identified dependencies of a project to provide the metadata for the identified components and to run a compliance check according to defined criteria, such as license compatibility, known security violations, company policies.

### Component Analysis Service
Dedicated tools and services which provide license information for source code and/or binaries. The tools used follow different approaches. Some get the information by looking it up in a database. Some do source code scans for copyright and license information in comments. Others scan the source code concerning copyrighted snippets. The clearing also contains a step in which the results are approved according to company criteria.

### Component Metadata Repository
A system or service that stores metadata about used software components (esp. FOSS). This includes licenses, copyrights, known vulnerabilitites and information, that is needed to do export classifications (ECCN), such as information about the contained cryptographic functionality. The information is used within the compliance checker to aquire the metadata for the identified components, to assess the compilation of dependent components and to provide the information for the creation of the FOSS bundle (i.e., the artifacts needed for the distribution of a software). The Component Metadata Repository can be linked to an external FOSS Metadata Database to retrieve commonly known information and make it usable within the organization. Also Security Vulnerability Database and other sources for e.g. export classification-relevant data, can be linked to retrieve the necessary information and to make it available within the company.
Example: [Eclipse SW360](https://projects.eclipse.org/proposals/sw360)

### Continuous Integration/Deployment Infrastructure (CI/CD)
Systems or services that orchestrate the build and deployment process for a software project and executes workflows triggered by different kind of events. The CI/CD infrastructure typically runs software builds and executes further build steps like testing and the compliance checks

### FOSS Compliance Bundle Generator
A tool that creates all the necessary documentation needed for the distribution of a software, such a document with all used components there licenses and copyrights, or a source code bundle with all the FOSS sources used in the project. The FOSS bundle is the artifact to be bundled with the delivered product to fulfill license obligations found in FOSS licenses.

### License & Copyright Scanner
A tool that analyses source code to identify license and copyright information.
Example: [Fossology](https://www.fossology.org/), [Scancode Toolkit](https://github.com/nexB/scancode-toolkit)

### License Metadata Repository
A list of all FOSS (and commercial?) licenses in use within an organization with all necessary metadata like implied obligations. It may use a Public License Master Database and a License Obligation Database for basic information enriched by the company for internal use.
Example: [Eclipse SW360](https://projects.eclipse.org/proposals/sw360)

### Product Metadata Repository
Software products and most software components are built from other software components. The Product Metadata Repository contains this relationship information to enable the management of dependencies over the life cycle of the software.
Example: [Eclipse SW360](https://projects.eclipse.org/proposals/sw360)

### Security Vulnerability Assessment
A set of tools and services which map known vulnerabilities from an external database to components used in products and assess the relevance and exploitability of the vulnerability concerning the usage pattern of the component in question.

### Source Code Repository
Systems or services that provide source code. This is typically (also) a version control system. For the compliance tooling, typically the source code is needed as a folder on a file share, i.e., the source code is already checked out by, e.g., the Continuous Integration infrastructure. 

