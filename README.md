# Advanced Coding: Visual Studio & GitHub Copilot

This repo is a companion to this session at Microsoft AI Tour, a worldwide tour of events.

![Session cover image with a bright "A" text in 3D over a yellow and green abstract background.](./img/EN-US_BRK432_tech.png)


## Session Desciption

This session will cover using GitHub Copilot to solve a real-world scenario
where an ecommerce application is having performance issues. GitHub Copilot
will be used to understand the unfamiliar codebase and then explore and apply a
solution.

## Learning Outcomes

* GitHub Copilot features can help in real-world scenarios
* Gain a thorough understanding of unknown codebases
* Speedup your development workflows with ease


## Technology Used

For this session, you will need Visual Studio with a Github account so that you can authenticate and use GitHub Copilot.

## Additional Resources and Continued Learning

If you are presenting these slides, you can find additional resources, including the slides for the presentation and session delivery materials [here](/session-delivery-resources/README.md).


| Resources          | Links                             | Description        |
|:-------------------|:----------------------------------|:-------------------|
| Advanced GitHub Copilot  | [Learn Module](https://learn.microsoft.com/en-us/training/modules/advanced-github-copilot/) | Learn about Advanced GitHub Copilot features |
| Visual Studio with GitHub Copilot Future Learning 2  | [Visual Studio](https://visualstudio.microsoft.com/github-copilot/) | Get the latest details on Visual Studio with Copilot |

## Content Owners

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<table>
<tr>
    <td align="center"><a href="http://learnanalytics.microsoft.com">
        <img src="https://github.com/alfredodeza.png" width="100px;" alt="Alflredo Deza
"/><br />
        <sub><b>Alfredo Deza
</b></sub></a><br />
            <a href="https://github.com/alfredodeza" title="talk">📢</a> 
    </td>
</tr>
<tr>
    <td align="center"><a href="http://learnanalytics.microsoft.com">
        <img src="https://github.com/elbruno.png" width="100px;" alt="Bruno Capuano
"/><br />
        <sub><b>Bruno Capuano
</b></sub></a><br />
            <a href="https://github.com/elbruno" title="talk">📢</a> 
    </td>
</tr>
</table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

## Responsible AI 

Microsoft is committed to helping our customers use our AI products responsibly, sharing our learnings, and building trust-based partnerships through tools like Transparency Notes and Impact Assessments. Many of these resources can be found at [https://aka.ms/RAI](https://aka.ms/RAI).
Microsoft’s approach to responsible AI is grounded in our AI principles of fairness, reliability and safety, privacy and security, inclusiveness, transparency, and accountability.

Large-scale natural language, image, and speech models - like the ones used in this sample - can potentially behave in ways that are unfair, unreliable, or offensive, in turn causing harms. Please consult the [Azure OpenAI service Transparency note](https://learn.microsoft.com/legal/cognitive-services/openai/transparency-note?tabs=text) to be informed about risks and limitations.

The recommended approach to mitigating these risks is to include a safety system in your architecture that can detect and prevent harmful behavior. [Azure AI Content Safety](https://learn.microsoft.com/azure/ai-services/content-safety/overview) provides an independent layer of protection, able to detect harmful user-generated and AI-generated content in applications and services. Azure AI Content Safety includes text and image APIs that allow you to detect material that is harmful. We also have an interactive Content Safety Studio that allows you to view, explore and try out sample code for detecting harmful content across different modalities. The following [quickstart documentation](https://learn.microsoft.com/azure/ai-services/content-safety/quickstart-text?tabs=visual-studio%2Clinux&pivots=programming-language-rest) guides you through making requests to the service.

Another aspect to take into account is the overall application performance. With multi-modal and multi-models applications, we consider performance to mean that the system performs as you and your users expect, including not generating harmful outputs. It's important to assess the performance of your overall application using [generation quality and risk and safety metrics](https://learn.microsoft.com/azure/ai-studio/concepts/evaluation-metrics-built-in).

You can evaluate your AI application in your development environment using the [prompt flow SDK](https://microsoft.github.io/promptflow/index.html). Given either a test dataset or a target, your generative AI application generations are quantitatively measured with built-in evaluators or custom evaluators of your choice. To get started with the prompt flow sdk to evaluate your system, you can follow the [quickstart guide](https://learn.microsoft.com/azure/ai-studio/how-to/develop/flow-evaluate-sdk). Once you execute an evaluation run, you can [visualize the results in Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/how-to/evaluate-flow-results).

