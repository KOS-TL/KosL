# KOS-TL 编译器 / KOS-TL Compiler

[中文](#中文) | [English](#english)

---

<a name="中文"></a>
## 中文

KOS-TL 语言的编译器实现，将 KOS-TL 源代码编译为 C 代码。

## 项目结构

```
compiler/
├── src/
│   ├── compiler/        # 编译器核心模块
│   │   ├── lexer.c      # 词法分析器
│   │   ├── parser.c     # 语法分析器
│   │   ├── type_checker.c  # 类型检查器
│   │   ├── codegen.c    # 代码生成器
│   │   └── ast.c        # AST 操作
│   └── main.c           # 编译器主程序
├── include/
│   └── compiler.h       # 编译器公共接口
├── examples/            # 示例 KOS-TL 代码
├── tests/               # 测试用例
└── CMakeLists.txt       # 构建配置
```

## 构建

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

## 使用

### 基本用法

```bash
# 编译KOS-TL文件为C代码
./kos-tl-compiler example.kos -o example.c

# 只进行类型检查（不生成代码）
./kos-tl-compiler example.kos -t

# 输出到标准输出
./kos-tl-compiler example.kos
```

### 命令行选项

- `-o <文件>`: 指定输出文件（默认：stdout）
- `-t`: 只进行类型检查，不生成代码
- `-h, --help`: 显示帮助信息
- `-v, --version`: 显示版本信息

### 编译流程

1. **词法分析**: 将源代码转换为Token流
2. **语法分析**: 构建抽象语法树（AST）
3. **类型检查**: 验证类型正确性
4. **代码生成**: 将AST转换为C代码

## 开发状态

- [x] 词法分析器 ✅
- [x] 语法分析器 ✅
- [x] 类型检查器 ✅（核心功能已实现）
  - [x] 类型环境管理
  - [x] 双向类型检查（检查模式和推断模式）
  - [x] 类型推断
  - [x] Universe层级检查
  - [x] AST到kos_term转换
  - [x] 类型相等性和兼容性检查
- [x] 代码生成器 ✅（基础实现已完成）
  - [x] AST到C代码转换框架
  - [x] 表达式代码生成
  - [x] 函数定义生成
  - [x] 类型声明生成
  - [x] 模块代码生成
- [x] 编译器主程序集成 ✅
  - [x] 命令行参数解析
  - [x] 文件I/O处理
  - [x] 完整编译流程集成
  - [x] 错误处理和报告

---

<a name="english"></a>
## English

# KOS-TL Compiler

Compiler implementation for the KOS-TL language, compiling KOS-TL source code to C code.

## Project Structure

```
compiler/
├── src/
│   ├── compiler/        # Compiler core modules
│   │   ├── lexer.c      # Lexer
│   │   ├── parser.c     # Parser
│   │   ├── type_checker.c  # Type checker
│   │   ├── codegen.c    # Code generator
│   │   └── ast.c        # AST operations
│   └── main.c           # Compiler main program
├── include/
│   └── compiler.h       # Compiler public interface
├── examples/            # Example KOS-TL code
├── tests/               # Test cases
└── CMakeLists.txt       # Build configuration
```

## Build

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

## Usage

### Basic Usage

```bash
# Compile KOS-TL file to C code
./kos-tl-compiler example.kos -o example.c

# Type checking only (no code generation)
./kos-tl-compiler example.kos -t

# Output to stdout
./kos-tl-compiler example.kos
```

### Command Line Options

- `-o <file>`: Specify output file (default: stdout)
- `-t`: Type checking only, no code generation
- `-h, --help`: Show help information
- `-v, --version`: Show version information

### Compilation Pipeline

1. **Lexical Analysis**: Convert source code to token stream
2. **Syntax Analysis**: Build abstract syntax tree (AST)
3. **Type Checking**: Verify type correctness
4. **Code Generation**: Convert AST to C code

## Development Status

- [x] Lexer ✅
- [x] Parser ✅
- [x] Type Checker ✅ (core functionality implemented)
  - [x] Type environment management
  - [x] Bidirectional type checking (check mode and infer mode)
  - [x] Type inference
  - [x] Universe level checking
  - [x] AST to kos_term conversion
  - [x] Type equality and compatibility checking
- [x] Code Generator ✅ (basic implementation completed)
  - [x] AST to C code conversion framework
  - [x] Expression code generation
  - [x] Function definition generation
  - [x] Type declaration generation
  - [x] Module code generation
- [x] Compiler Main Program Integration ✅
  - [x] Command line argument parsing
  - [x] File I/O handling
  - [x] Complete compilation pipeline integration
  - [x] Error handling and reporting






