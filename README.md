# AI大模型横向评测框架 (AI Model Evaluation Framework)

这是一个轻量级的自动化评测框架，旨在对不同的大语言模型（LLM）在多个维度的能力进行快速、直观的横向对比。

![客观能力总结图](objective_summary.png)
![主观能力总结图](subjective_summary.png)
*(上图为本框架自动生成的两张评测结果可视化图表)*

---

## 项目目标

- **自动化评测**：通过API调用，自动化地对多个模型进行批量提问。
- **多维度衡量**：基于一个自建的小型Benchmark，从客观（逻辑、安全）和主观（创意、共情）两个维度进行评测。
- **结果可视化**：生成直观的对比报告和数据图表，方便快速定位模型间的差异。

## 工作流程

1.  **配置与运行**：在 `run_evaluation.py` 脚本中，配置需要评测的AI模型列表和Benchmark问题集。
2.  **安全输入Token**：运行脚本时，程序会提示你在命令行中安全地输入你的Hugging Face Access Token，它不会被保存到任何文件中。
3.  **API调用与报告生成**：脚本循环调用各个模型，并将结果自动整理成一个结构化的Markdown文件 (`evaluation_report.md`)。
4.  **双图表可视化**：脚本会根据评测结果，分别生成客观能力和主观能力的总结性柱状图。

## 如何运行

1.  **准备环境**:
    ```bash
    # 安装必要的Python库
    python -m pip install openai matplotlib
    ```
2.  **开始评测**:
    ```bash
    # 直接运行主脚本
    python run_evaluation.py
    ```
3.  **输入Token**:
    在终端提示 “请粘贴你的Hugging Face Access Token...” 时，粘贴你的Token并按回车。

4.  **查看结果**:
    程序运行结束后，你会在文件夹里找到 `evaluation_report.md` 和两张 `.png` 成果文件。

## 安全提示

**永远不要**将你的 `Access Token` 或任何密码、密钥等敏感信息直接写在代码里并上传到GitHub。本项目采用了在运行时输入的方式，确保了你的密钥安全。

---
本项目由个人学习和探索完成，旨在快速搭建一个可用的、安全的评测原型。
