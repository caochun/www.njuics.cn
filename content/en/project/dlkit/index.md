+++
# Project title.
title = "NAP-DLP"

# Date this page was created.
date = 2019-04-01T00:00:00

# Project summary to display on homepage.
summary = "Kubernetes-based Runtime Platform for Deep Learning"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["Deep Learning"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = "example-slides"

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
links = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Photo by rawpixel on Unsplash"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

深度学习，作为机器学习的分支，伴随着模型能力和计算能力的提升，在机器学习领域有着举足轻重的地位。目前深度学习的模型已成为很多行业的系统中不可或缺的部分。在2006年，Hinton等人提出深度置信网络(Deep Belief Network) [11]，通过贪心式的逐层训练，成功将非监督学习的深层神经网络的参数进行分层训练。随后，多种形式的深度神经网络被提出，如深层的自编码器(Autoencoder) [12]。然而，对于这类深层结构的神经网络而言，其参数数量庞大，无法有效通过反向传播方法对模型参数进行整体的有效训练。为了解决深度神经网络有效训练的问题，研究者将眼光落在卷积神经网络。卷积神经网络[10]最早由LeCun等人提出，并用于手写体数字识别的任务中。卷积神经网络的优势在于可大幅降低网络中的参数数量。随着研究者的不懈努力，设计出诸如Inception[9]，VGG[8]等深度卷积神经网络，这些网络能够有效完成复杂图像的识别任务。这一方面的技术突破，使得很多机器视觉相关的图像识别任务，如人脸识别，自动驾驶中的路况识别等，有了实质性的解决方案。

除了模型能力的提升，计算能力的提升也是深度学习能够飞速发展的必要因素之一。借助GPU可进行高效矩阵运算的能力，目前的深度学习任务多将计算放置于GPU上运行。与此同时，由于深度学习的任务体量相对庞大，训练过程非常耗时。对于目前大级别数据集上的训练任务而言，任务在单GPU上运行同样非常耗时，复杂的深度神经网络的训练任务通常需要几天，甚至一两周的时间完成。然而，由于训练过程可并行的特性，使训练任务并行化处理成为业界的基本手段。

目前，业界多采用分布式的架构进行深度学习模型的训练和使用，如今主流的深度学习框架也都支持分布式环境下的模型运行。具体而言，为了加速模型训练，企业及学术机构通常在一个大规模的共享资源集群上搭建云计算资源平台来执行深度学习训练任务。与大数据分析任务相同，该共享资源计算集群需要一个高效的资源调度器来处理多租户的训练任务在同一个共享资源集群上的执行。传统的通用型集群资源调度器例如Mesos[1]，YARN[2]，Borg[3]，可以在大规模集群上处理不同类型的任务，例如长时间服务型任务、分布式计算任务等。TetrisSched[4]可以处理周期性执行的数据并行任务，并为任务设定固定的资源预留值以保证任务执行期间的性能。
然而对于深度学习训练任务，尤其是并行训练任务，对集群资源调度器有着更为严格的约束和要求。这类任务通常以资源消耗高，训练时间长为特点，例如在LibriSpeech数据集上训练一个DeepSpeech2[5]的模型，即便分配了16块GPU也需要消耗近3到5天才能得到一个令人满意的精度。同时训练任务往往包含大量的浮点计算，需要配合例如GPU等硬件加速器。而GPU又不同于CPU，在硬件层面较难做到多任务细粒度共享同一块设备。因此需要在通过软件机制，例如调度策略上的控制，来进行多任务在GPU集群上高效执行。此外，多GPU训练任务通常要求较高的数据本地性以减少训练过程中的参数交换通信开销，而不同的训练任务若同时运行在同一个计算节点上又会出现相互影响的状况。调度器同时还需要解决训练任务内和任务间的亲和性及反亲和性的问题。

当前云计算支撑平台上的调度器未考虑深度学习训练任务的特殊性，只能将其作为普通的计算任务对待，这会导致集群的资源利用率低以及训练效率差。此外面向深度学习任务的云计算平台还需要解决深度学习训练繁琐的过程，尤其是并行训练过程，需要简化任务提交，资源设定等问题，让算法工作者仅需要关心算法本身。
