<h1 align="center">Large Model Basics</h1>


<div align="center">
  <img src=".\figure\cover.png" style="width: 50%">
</div>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue">
  <img src="https://img.shields.io/github/stars/ZJU-LLMs/Foundations-of-LLMs?style=social">
  <img src="https://img.shields.io/github/forks/ZJU-LLMs/Foundations-of-LLMs?style=social">
<!-- <img src="https://img.shields.io/github/license/ZJU-LLMs/Foundations-of-LLMs"> -->
</p>

This book aims to systematically explain the relevant basic knowledge and introduce cutting-edge technologies for readers who are interested in large language models. The author team will listen carefully to the suggestions of the open source community and experts and scholars, and continue to make **monthly updates**, and strive to create **easy-to-read, rigorous, and in-depth** large model textbooks. In addition, this book will also be equipped with a relevant **Paper List** for each chapter to track the **latest progress** of related technologies.

The first edition of this book includes six chapters: **Traditional Language Model**, **Evolution of Large Language Model Architecture**, **Prompt Engineering**, **Efficient Parameter Fine-tuning**, **Model Editing**, **Retrieval Enhanced Generation**. To increase the readability of this book, each chapter uses **an animal** as the background to illustrate specific technologies, so this book uses six animals as the cover. The content contained in the current version is derived from the author team's exploration and understanding of related directions. If there are any errors, please raise more issues and give more advice. In the future, the author team will continue to explore directions such as large model reasoning acceleration and large model intelligent agents. Relevant content will also be added to subsequent versions of this book, and we look forward to more and more animals on the cover.

The current complete PDF version path of this book is <a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%20%E5%AE%8C%E6%95%B4%E7%89%88.pdf">Large Model Foundation.pdf</a>. In addition, we also provide two folders, <a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/tree/main/%E3%80%8A%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E5%88%86%E7%AB%A0%E8%8A%82%E5%86%85%E5%AE%B9">Large Language Model Chapter Content</a> folder contains the PDF version of each chapter. The <a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/tree/main/%E5%A4%A7%E6%A8%A1%E5%9E%8B%E7%BB%8F%E5%85%B8%E8%AE%BA%E6%96%87%E5%88%97%E8%A1%A8">Large Language Model Related Papers</a> folder contains relevant papers for each chapter and is currently being updated.

The table of contents for each chapter is shown below.

## Table of Contents

<table>
    <tr>
        <th style="text-align:center; width: 25%;">Chapter</th>
        <th style="text-align:center; width: 75%;" colspan="3">Contents</th>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4%A7%E 6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A4%A7%E6%A Chapter 1: Language Model Basics
        <td style="width: 25%;">1.1 Language model based on statistical methods</td>
        <td style="width: 25%;">1.2 RNN-based language model</td>
        <td style="width: 25%;">1.3 Transformer-based language model</td>
    </tr>
    <tr>
        <td>1.4 Sampling Methods of Language Models</td>
        <td>1.5 Evaluation of Language Models</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4%A7%E6%A 8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A4%A7%E6%A8%A1% Chapter 2: Large Language Models
        <td>2.1 Big Data + Big Model → New Intelligence</td>
        <td>2.2 Overview of Large Language Model Architecture</td>
        <td>2.3 Large Language Model Based on Encoder-only Architecture</td>
    </tr>
    <tr>
        <td>2.4 Large Language Model Based on Encoder-Decoder Architecture</td>
        <td>2.5 Large Language Model Based on Decoder-only Architecture</td>
        <td>2.6 Non-Transformer Architecture</td>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A 4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A% E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E5%88%86%E7%AB%A0%E8%8A% 82%E5%86%85%E5%AE%B9/%E7%AC%AC3%E7%AB%A0%20Prompt%20%E5%B7%A5%E7%A8%8B.pdf">No. 3 Chapter: Prompt Project</a></b></td>
        <td>3.1 Prompt Project Introduction</td>
        <td>3.2 Contextual Learning</td>
        <td>3.3 Thinking Chain</td>
    </tr>
    <tr>
        <td>3.4 Prompt Tips</td>
        <td>3.5 Related Applications</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4%A7%E 6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A4%A7%E6%A Chapter 4: Efficient Parameter Fine-tuning
        <td>4.1 Introduction to Efficient Parameter Fine-tuning</td>
        <td>4.2 Parameter addition method</td>
        <td>4.3 Parameter selection method</td>
    </tr>
    <tr>
        <td>4.4 Low-rank adaptation method</td>
        <td>4.5 Practice and Application</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4% A7%E6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A Chapter 5: Model Editing
        <td>5.1 Introduction to Model Editing</td>
        <td>5.2 Classical methods for model editing</td>
        <td>5.3 Additional parameter method: T-Patcher</td>
    </tr>
    <tr>
        <td>5.4 Positioning Editing Method: ROME</td>
        <td>5.5 Model Editing Application</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2"><b><a href="https://github.com/ZJU-LLMs/Foundations-of-LLMs/blob/main/%E3%80%8A%E5%A4%A7%E 6%A8%A1%E5%9E%8B%E5%9F%BA%E7%A1%80%E3%80%8B%E6%95%99%E6%9D%90/%E3%80%8A%E5%A4%A7%E6%A Chapter 6: Retrieval Enhanced Generation
        <td>6.1 Introduction to search enhancement generation</td>
        <td>6.2 Retrieval Enhancement Generation Architecture</td>
        <td>6.3 Knowledge Retrieval</td>
    </tr>
    <tr>
        <td>6.4 Build Enhancements</td>
        <td>6.5 Practice and Application</td>
        <td></td>
    </tr>
</table>






## Acknowledgements

The continuous improvement of this book will rely on the help and support of all readers. Your suggestions will be our driving force to move forward!

We list all the people who raised issues here to express our deep gratitude.




If you have other questions about this book, please feel free to contact us by sending an email to: xuwenyi@zju.edu.cn.

<div align="center">
  <img src=".\figure\wechat_QR_code.jpg" style="width: 90%">
</div>
