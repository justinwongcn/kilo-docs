---
sidebar_label: GCP Vertex AI
---

# 在 Kilo Code 中使用 GCP Vertex AI

Kilo Code 支持通过 Google Cloud Platform 的 Vertex AI 访问模型，这是一个托管的机器学习平台，提供对多种基础模型的访问，包括 Anthropic 的 Claude 系列。

**网站:** [https://cloud.google.com/vertex-ai](https://cloud.google.com/vertex-ai)

## 先决条件

*   **Google Cloud 账户:** 您需要一个活跃的 Google Cloud Platform (GCP) 账户。
*   **项目:** 您需要一个启用了 Vertex AI API 的 GCP 项目。
*   **模型访问权限:** 您必须请求并获准访问您想要使用的特定 Claude 模型。请参阅 [Google Cloud 文档](https://cloud.google.com/vertex-ai/generative-ai/docs/partner-models/use-claude#before_you_begin) 获取说明。
*   **应用程序默认凭据 (ADC):** Kilo Code 使用应用程序默认凭据来与 Vertex AI 进行身份验证。最简单的设置方法是：
    1.  安装 Google Cloud CLI: [https://cloud.google.com/sdk/docs/install](https://cloud.google.com/sdk/docs/install)
    2.  使用以下命令进行身份验证：`gcloud auth application-default login`

## 支持的模型

Kilo Code 通过 Vertex AI 支持以下模型（基于源代码）：

*   **Google Gemini 模型:**
    *   `gemini-2.0-flash-001`
    *   `gemini-2.5-pro-exp-03-25`
    *   `gemini-2.0-pro-exp-02-05`
    *   `gemini-2.0-flash-lite-001`
    *   `gemini-2.0-flash-thinking-exp-01-21`
    *   `gemini-1.5-flash-002`
    *   `gemini-1.5-pro-002`
*   **Anthropic Claude 模型:**
    *   `claude-3-7-sonnet@20250219:thinking`
    *   `claude-极客3-7-sonnet@20250219`
    *   `claude-3-5-sonnet-v2@20241022`
    *   `claude-3-5-sonnet@20240620`
    *   `claude-3-5-haiku@20241022`
    *   `claude-3-opus@20240229`
    *   `claude-3-haiku@20240307`

请参阅 [Google Cloud 关于 Vertex AI 模型的文档](https://cloud.google.com极客/vertex-ai/generative-ai/docs/learn/models) 获取最新可用模型及其 ID 列表。

## 在 Kilo Code 中配置

1.  **打开 Kilo Code 设置:** 点击 Kilo Code 面板中的齿轮图标 (<Codicon name="gear" />)。
2.  **选择提供商:** 从 "API 提供商" 下拉菜单中选择 "GCP Vertex AI"。
3.  **输入项目 ID:** 输入您的 Google Cloud 项目 ID。
4.  **选择区域:** 选择您的 Vertex AI 资源所在的区域 (例如 `us-east5`)。
5.  **选择模型:** 从 "模型" 下拉菜单中选择您想要的模型。

## 提示和注意事项

*   **权限:** 确保您的 Google Cloud 账户具有访问 Vertex AI 和您想要使用的特定模型所需的权限。
*   **定价:** 请参阅 [Vertex AI 定价](https://cloud.google.com/vertex-ai/pricing) 页面了解详情。