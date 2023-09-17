# Video-Text Retrieval Project README

## Introduction

Welcome to the repository for the Video-Text Retrieval project, developed as part of an internship at the **University of Hamburg**. This project focuses on creating a proof-of-concept (PoC) application for Video-Text Retrieval (Video-IR). The primary goal is to build a tool capable of retrieving relevant video scenes based on user input text queries. The project utilizes the MSR-VTT dataset, a rich source of diverse video content and associated textual descriptions.

### Zero-Shot Learning with Xclip

A key highlight of this project is the adoption of zero-shot learning techniques. Instead of relying solely on captions, our retrieval model is trained using a combination of visual and textual information, leveraging the powerful Xclip model. Xclip is a pre-trained model capable of encoding both images and text into a shared latent space, enabling seamless multimodal retrieval. It consists of two decoders, one for text and another for video, making it particularly suitable for video-text retrieval tasks.

In this project, various variants of the Xclip model were employed to explore different model architectures and compare their performance. The utilized variants include:
- `microsoft/xclip-base-patch32`
- `microsoft/xclip-base-patch16`
- `microsoft/xclip-large-patch14`

The distinctions among these variants lie in their architectures, the number of patches used, and the training data employed.

### Understanding Xclip Model and Patching

The Xclip model employs a technique called patching, which divides an input image into a grid of smaller rectangular regions or patches. Visual features are then extracted from each patch using a convolutional neural network (CNN). These visual features are combined with textual features extracted from the input text, resulting in a unified representation. In the context of the Xclip model, "patches" refer to the spatial regions of the input image that the CNN model uses for feature extraction.

#### Variant Specifics:
- `microsoft/xclip-base-patch32` and `microsoft/xclip-base-patch16` have a base architecture with 32 and 16 patches, respectively, which contributes to their unique capabilities.
- `microsoft/xclip-large-patch14` boasts a more complex architecture with 14 patches, which enhances its performance for certain tasks.

## Components

To enable video-text retrieval, this project is divided into five key components:

### Component 1: Video Scene Segmentation
This component focuses on dividing input videos into smaller scenes, making them amenable to analysis and indexing for retrieval.

### Component 2: XCLIP Embedding Computation
In this stage, we compute the Xclip embeddings for each scene. Xclip's capabilities in encoding images and text into a shared latent space enable seamless multimodal retrieval.

### Component 3: FAISS Indexing
This component involves persisting the scene embeddings into a FAISS index. FAISS is a highly efficient similarity search library used for retrieving similar embeddings based on cosine similarity.

### Component 4: Scene Retrieval Program
The heart of the project, this component implements the retrieval program. It takes a user's text query as input, retrieves relevant scene embeddings from the FAISS index, and returns the top-scoring scenes.

### Component 5: User Interface
The user interface component provides an intuitive platform for users to input their queries and visualize the retrieved scenes. It enhances the usability of the retrieval tool.

This README provides an overview of each component and includes screenshots of the user interface, detailed explanations of the underlying algorithms, and insights into the CNN image processing techniques employed by Xclip.

For in-depth details and instructions on how to use each component, please refer to the respective documentation within this repository.

Thank you for your interest in our Video-Text Retrieval project!
