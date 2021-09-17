# SIGSOFT Artifact Evaluation Working Group
SIGSOFT conferences organize artifact evaluation processes to recognize authors’ efforts towards ensuring that their tools and datasets are available and reusable, and moreover, to integrate these artifacts into our publication process. SIGSOFT’s artifact evaluation process started at ESEC/FSE in 2011, and has now spread to become commonplace at most of our conferences. In the intervening time, we have learned a lot about and refined the process. However, we are still not done: recent studies (currently under review) have shown that there is confusion on the part of both reviewers and authors. Authors are uncertain of the effort needed to prepare an artifact that passes the muster of the artifact review committee. Through these studies, reviewers also report that without clear criteria for acceptance, it is difficult to calibrate reviews and conduct the process fairly.

The primary goals of this working group are to document and guide our community’s norms in artifact evaluation in an effort to increase author and reviewer participation. While it is ultimately the authors’ choice to submit an artifact or not, our goal is to ensure that the process is as transparent and seamless as possible, and ultimately, for artifact submission to become the norm. If authors perceive that the criteria for acceptance is higher than it is, they will be discouraged from submitting: we aim to clarify the evaluation process. In many SIGSOFT conferences, authors can short-circuit the review process and instead be rewarded with an "Artifact Available" badge, and a link to that artifact included in the ACM Digital Library. However, this irregularly documented and typically unadvertised, and it is unclear if this should be a formal policy or not.

### Contributing
Our first step is to identify relevant questions that we should discuss as a community. Below, please find a summary of the instructions typically given at SIGSOFT conferences and a list of discussion points. If you have suggestions for how we should normalize these issues, please comment on them (using the GitHub issue tracking system - each topic links to an issue). If you have suggestions for other topics to discuss, [open an issue](https://github.com/acmsigsoft/artifact-evaluation/issues/new). After discussion, we will begin the process of drafting new, more detailed guidance for artifact evaluation committees and authors.

## Artifact Evaluation at SIGSOFT Conferences Today

The following instructions are typically provided to all authors of artifacts at SIGSOFT conferences:

* Artifacts must be documented. Each artifact should have a README file containing:
	* How to install the artifact, how to run the artifact, and how to compare the output of the artifact with the outputs described in the paper
	* A  clear listing of claims that are described in the paper, along with an explanation of how each of those claims is supported by the artifact
	* Step-by-step instructions to execute the artifact
	* Instructions for reviewers to “play” with the artifact, allowing reviewers to construct new input data to test the artifact's robustness
* Artifacts must be licensed. Each artifact should have a LICENSE file containing:
    * How the artifact can be accessed and reviewed
    * How the artifact can be used by researchers for reproduction
    * How the artifact can be reused by people in academia or industry
    * It is not a SIGSOFT requirement that artifacts must be open source,
      but the license must specify to which extend the artifact can be (re)used
    * It is recommended to use standard licenses, see https://spdx.org/licenses/
* Artifacts must be fully self-contained
	* Ideally, software artifacts will be contained within a VM, which contains all of the artifact’s dependencies, reducing the likelihood that the artifact decays over time.
	* Take caution with using docker images: Typically the goal with a docker container is to distribute a base container and then a script to install dependencies in that container. While this reduces the size of the artifact, it increases reliance on external systems, and hence, the artifact may stop working eventually. When using a docker container, be sure that what you distribute is fully self-contained.
	* Non-software artifacts (e.g. datasets) should be distributed as a single archive (no need for a VM)


## <a name="discussion-points"></a>Discussion Points
Based on community feedback, we believe that it is worthwhile to discuss the following points (each is linked to a corresponding GitHub issue for discussion):

* **[Completeness and size](https://github.com/acmsigsoft/artifact-evaluation/issues/1):** Must the artifact provide data and tools to replicate ALL experiments in a paper, or is it allowable to scope an artifact to consider only part of the claims? Who decides (authors, reviewers or chairs) what claims in a given paper should be supported by the artifact? What should we consider "too much data" or "too long of an experiment" that can’t be submitted in full for artifact evaluation? For instance, one researcher might consider a 2GB dataset too large to submit in full, while another might submit a 2TB dataset. Whatever the criteria for "too big" is - what process should authors follow if their artifact is too big to submit some subset of their artifact for evaluation?
* **[Automation](https://github.com/acmsigsoft/artifact-evaluation/issues/2):** Should an artifact automatically generate any tables/graphs that appear in a paper, or is it OK (or, perhaps even better, given the potential for mistakes in these scripts) for this to be a somewhat manual process?
* **[Data analysis](https://github.com/acmsigsoft/artifact-evaluation/issues/3):** For empirical artifacts: must an artifact include both the “raw” pre-processed data, and the post-processed (as analyzed) data?
* **[Extendability](https://github.com/acmsigsoft/artifact-evaluation/issues/4):** To what extent should reviewers try to extend an artifact (build on a tool, analyze a dataset in a new way, or provide new inputs/configurations to that tool or analysis), in comparison to simply running it?
* **[Communication](https://github.com/acmsigsoft/artifact-evaluation/issues/5):** How much communication should be allowed between evaluators and authors during the review period?
* **[Low-overhead available badge](https://github.com/acmsigsoft/artifact-evaluation/issues/6):** Currently, the publisher will apply the "Artifact Available" badge to the camera ready of a paper if the authors submit a DOI for their artifact. The publisher might check that the DOI is valid, but certainly will not check the contents of that artifact (e.g. it might be empty). Should there be a review process at all for "Artifact Available?" ICSE 2020 has one, ISSTA 2019 did not.
* **[Replicated/Reproduced/Functional clarifications](https://github.com/acmsigsoft/artifact-evaluation/issues/7):** Currently, there is some confusion on the "Results Replicated" and "Results Reproduced" badges. The process for reviewing, reporting, and retroactive badge awarding needs to be clarified. FSE 2018 and 2019, ICSE 2019 and 2020 do not award the "Functional" badge. Is this a good practice? Should we generally move away from this badge?


We seeded this list with personal observations, and make no claims to have covered all (or perhaps even any) of the important topics related to artifact evalaution processes. If you would like to propose another topic to discuss, please [open an issue](https://github.com/acmsigsoft/artifact-evaluation/issues/new) for it.
