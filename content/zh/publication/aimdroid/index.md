+++
title = "AimDroid: Activity-Insulated Multi-level Automated Testing for Android Applications"
date = 2013-07-01T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["admin", "Robert Ford"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference paper
# 2 = Journal article
# 3 = Preprint / Working Paper
# 4 = Report
# 5 = Book
# 6 = Book section
# 7 = Thesis
# 8 = Patent
publication_types = ["1"]

# Publication name and optional abbreviated version.
publication = "In *Source Themes Conference*"
publication_short = "In *STC*"

# Abstract.
abstract = "Activities are the fundamental components of Android applications (apps). However, existing approaches to automated testing for Android apps cannot effectively manage the transitions between activities, e.g., too rarely or too often. Besides, some techniques need to repeatedly restart from scratch and revisit every intermediate activity to reach a specific one, which leads to unnecessarily long transitions and wasted time. To address these problems, we propose AimDroid, a practical model-based approach to automated testing for Android apps that aims to manage the exploration of activities and meantime minimize unnecessary transitions between them. Specifically, AimDroid applies an activity-insulated multi-level strategy during testing and replaying. It systematically discovers unexplored activities and then intensively exploits every discovered individual with a reinforcement learning guided random algorithm. We conduct comprehensive experiments on 50 popular closed-source commercial apps that in total have billions of daily usages in China. The results demonstrate that AimDroid outperforms both Sapienz and Monkey in activity, method and instruction coverage, respectively. In addition, AimDroid also reports more crashes than the other two."

# Summary. An optional shortened abstract.
summary = "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum."

# Digital Object Identifier (DOI)
doi = ""

# Is this a featured publication? (true/false)
featured = true

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Source Themes"]

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["internal-project"]

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = "example"

# Links (optional).
url_pdf = "http://eprints.soton.ac.uk/352095/1/Cushen-IMV2013.pdf"
url_code = "#"
url_dataset = "#"
url_project = ""
url_slides = ""
url_video = "#"
url_poster = "#"
url_source = "#"

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
links = [{name = "Custom Link", url = "http://example.org"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

{{% alert note %}}
Supplementary notes can be added here, including [code and math](https://sourcethemes.com/academic/docs/writing-markdown-latex/).
{{% /alert %}}