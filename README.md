![](images_mrhub/MRHub_banner.png)

This is the GitHub repository associated with the MR-Hub website - a platform to share information about open source software relevant to the [ISMRM](http://www.ismrm.org) community.

This version of the page was created during the recent [MRI-themed Hackathon](http://mrathon.github.io) and during the ISMRM meeting in Montreal. It is not quite ready yet to accept pull-requests to add new software - but if you have suggestions for additional features at this stage please add them to the 'issues' section.

Currently we are using the number of citations that [Semantic Scholar](http://www.semanticscholar.org) (this is used because of its API which is free to use) finds on the main paper associated with the software to allow sorting by a proxy metric related to 'impact' of the software. We realise that this is not a perfect solution, not least because not everyone who cites a paper uses the software - and not everyone who uses software has cited the paper. For now this seems like a reasonable solution - but feel free to use the 'issues' section to discuss any issues that arise due to this choice, along with any suggestions you might have for how to improve it.

A script which is run separately on an admin computer (`_data/getCitationsAndLastUpdate.m`) every few months will allow automatic updating of the number of citations and the date the software was last updated (using GitHub / Bitbucket APIs to retrieve last commit date).

### Submission instructions:
The database of packages is stored in the `_data` folder of this repository and is called `projects.json`. To add your own package:

1. Download the template file for the JSON file (`_data/template.json`) to your own computer 
2. Fill in all the fields - if you're unsure about any of the formatting take a look through the `projects.json` file to see how it was done for other packages. Watch out for the following fields which may not be obvious:
   * `"imageFile"` - this is the name of the logo image for your package. **Upload this file separately to the `images_packages` folder of this repo.** We don't currently have specific restrictions on the logo shape/size - but it seems to work well if it's at least 100 px high and no more than 250px wide, and a .png with a transparent background. Once we have more logos from different packages we can look at improving the visual layout of the site.
   * `"extraResources"` - Currently we have examples of packages with video tutorials which can be directly linked from the software description. If you have a Jupyter Notebook, for example (or anything similar!), which acts as a quick way to visualise how the software works, this would also be a great thing to add here. For the time-being, if you add anything other than 'Video Tutorial' it will not automagically appear on the website - so please contact [Dan Gallichan](mailto:gallichand@cardiff.ac.uk) if you would like to do this.
   * `"citationSearchString"` - As we are currently using [Semantic Scholar](http://www.semanticscholar.org) to provide the citation count for the main paper associated with the software, this field is used to uniquely identify the paper. This is straightforward for full papers, as they typically have a DOI, and this can be used directly. Semantic Scholar also finds ISMRM abstracts - but as these don't historically have a DOI, you'll need to put the paperID from Semantic Scholar here. See the separate section below for identifying the Semantic Scholar paperID in general. **Please let me know if your paper isn't in Semantic Scholar at all!** - this is still in the trial phase to see if such an approach is feasible - please contact [Dan Gallichan](mailto:gallichand@cardiff.ac.uk) if you can't find your paper and we'll see what else we might be able to do (it seems it should be possible to 'submit' your own paper to their database...)
   
   
   
   
#### Identifying the Semantic Scholar paperID if no DOI is available.
