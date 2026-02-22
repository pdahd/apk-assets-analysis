# Repository Agent Context: APK Text Analyzer

### Repository Purpose
本仓库专门用于分析 Android APK 反编译后的长文本文件。这些文件包含大量冗余混淆信息，核心任务是进行关键信息提炼。

### Data Processing Logic (Tools & Conventions)
- **Text Extraction Agent**: 负责扫描 `.txt`, `.xml`, `.json` 文件。
- **Input Context**: 原始文件通常位于 `/decompiled_files`。
- **Output Convention**: 所有分析结果必须生成在 `/analysis_results` 目录下，并以 `[文件名]_summary.txt` 命名。

### Operational Guidelines for Jules
1. **优先过滤**: 自动忽略混淆的类名（如 a.b.c）和无意义的资源 ID。
2. **提取重点**: 识别硬编码的服务器地址、API 接口、加密算法关键字（AES, RSA）及第三方 SDK 初始化参数。
3. **长文本处理**: 面对超过 5000 行的文件，请先生成结构化大纲，再针对关键段落进行详细提炼。

