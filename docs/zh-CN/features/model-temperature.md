# 模型温度

温度控制控制着 AI 模型输出的随机性。调整此设置可以优化不同任务的结果 - 从精确的代码生成到创意头脑风暴。温度是控制 AI 行为最强大的参数之一。经过良好调优的温度设置可以显著提高特定任务响应的质量和适用性。

<img src="/docs/img/model-temperature/model-temperature.gif" alt="展示温度滑块调整的动画" width="100%" />

## 什么是温度？

温度是一个设置（通常在 0.0 到 2.0 之间），用于控制 AI 输出的随机性或可预测性。找到合适的平衡点很关键：较低的值使输出更加集中和一致，而较高的值则鼓励更多的创造性和多样性。对于许多编码任务，适中的温度（大约 0.3 到 0.7）通常效果很好，但最佳设置取决于你想要实现的目标。

:::info 温度和代码：常见误解
温度控制输出随机性，而不是直接控制代码质量或准确性。关键点：

*   **低温（接近 0.0）：** 产生可预测、一致的代码。适用于简单任务，但可能重复且缺乏创造性。它不保证代码更好。
*   **高温：** 增加随机性，可能导致创造性解决方案，但也可能产生更多错误或无意义的代码。它不保证代码质量更高。
*   **准确性：** 代码准确性取决于模型的训练和提示的清晰度，而不是温度。
*   **温度 0.0：** 对一致性很有用，但限制了解决复杂问题所需的探索。
:::

## Kilo Code 中的默认值

Kilo Code 对大多数模型使用默认温度 0.0，优化代码生成的最大确定性和精确性。这适用于 OpenAI 模型、Anthropic 模型（非思考变体）、LM Studio 模型和大多数其他提供者。

一些模型使用更高的默认温度 - DeepSeek R1 模型和某些以推理为重点的模型默认温度为 0.6，在确定性和创造性探索之间提供了平衡。

具有思考能力的模型（AI 显示其推理过程）需要固定的温度 1.0，无法更改，因为此设置确保了思考机制的最佳性能。这适用于任何启用了 ":thinking" 标志的模型。

一些特殊模型根本不支持温度调整，在这种情况下，Kilo Code 会自动尊重这些限制。

## 何时调整温度

以下是一些适用于不同任务的温度设置示例：

*   **代码模式（0.0-0.3）：** 用于编写精确、正确的代码，具有一致的确定性结果
*   **架构模式（0.4-0.7）：** 用于头脑风暴架构或设计解决方案，平衡创造性和结构
*   **问答模式（0.7-1.0）：** 用于需要多样化和有洞察力的响应的解释或开放式问题
*   **调试模式（0.0-0.3）：** 用于以一致的精确性排除故障

这些都是起点 - 重要的是[尝试不同的设置](#experimentation)以找到最适合你特定需求和偏好的设置。

## 如何调整温度

1.  **打开 Kilo Code 面板：** 点击 VS Code 侧边栏中的 Kilo Code 图标（<img src="/docs/img/kilo-v1.svg" width="12" />）
2.  **打开设置：** 点击右上角的 <Codicon name="gear" /> 图标
3.  **找到温度控制：** 导航到提供者部分
4.  **启用自定义温度：** 勾选 "使用自定义温度" 复选框
5.  **设置你的值：** 将滑块调整为你偏好的值

    <img src="/docs/img/model-temperature/model-temperature.png" alt="Kilo Code 设置面板中的温度滑块" width="550" />
    *Kilo Code 设置面板中的温度滑块*

## 使用 API 配置配置文件设置温度

创建多个具有不同温度设置的[API 配置配置文件](/features/api-configuration-profiles)：

**如何设置特定任务的温度配置文件：**

1. 创建专门配置文件，如 "代码 - 低温"（0.1）和 "问答 - 高温"（0.8）
2. 为每个配置文件配置适当的温度设置
3. 使用设置或聊天界面中的下拉菜单在配置文件之间切换
4. 为每个模式设置不同的默认配置文件，以便在更改模式时自动切换

这种方法无需手动调整即可优化特定任务的模型行为。

## 技术实现

Kilo Code 实现温度处理时考虑以下因素：

*   用户定义的设置优先于默认值
*   尊重提供者特定的行为
*   强制执行模型特定的限制：
    *   启用思考的模型需要固定的温度 1.0
    *   一些模型不支持温度调整

## 实验

尝试不同的温度设置是发现最适合你特定需求的最有效方法：

### 有效的温度测试

1. **从默认值开始** - 以 Kilo Code 的预设值（大多数任务为 0.0）作为基线
2. **逐步调整** - 以小步长（±0.1）更改值以观察细微差异
3. **一致测试** - 在不同温度设置下使用相同的提示进行有效比较
4. **记录结果** - 记下哪些值对特定类型的任务产生最佳结果
5. **创建配置文件** - 将有效设置保存为[API 配置配置文件](/features/api-configuration-profiles)以便快速访问

请记住，不同的模型可能对相同的温度值有不同的响应，而启用思考的模型无论你的设置如何，始终使用固定的温度 1.0。

## 相关功能

- 与 Kilo Code 支持的所有[API 提供者](/providers/openai)一起使用
- 与[自定义指令](/advanced-usage/custom-instructions)相辅相成，用于微调响应
- 与你创建的[自定义模式](/features/custom-modes)一起使用