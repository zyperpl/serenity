set(SOURCES
    AST/AST.cpp
    AST/ASTPrinting.cpp
    Compiler/CompilerPass.cpp
    Compiler/ControlFlowGraph.cpp
    Compiler/GenericASTPass.cpp
    Compiler/Passes/CFGBuildingPass.cpp
    Compiler/Passes/CFGSimplificationPass.cpp
    Compiler/Passes/DeadCodeEliminationPass.cpp
    Compiler/Passes/IfBranchMergingPass.cpp
    Compiler/Passes/ReferenceResolvingPass.cpp
    Compiler/Passes/SSABuildingPass.cpp
    Parser/CppASTConverter.cpp
    Parser/Lexer.cpp
    Parser/SpecParser.cpp
    Parser/TextParser.cpp
    Parser/XMLUtils.cpp
    DiagnosticEngine.cpp
    Function.cpp
    main.cpp
)

lagom_tool(JSSpecCompiler LIBS LibCpp LibMain LibXML LibCrypto)
target_include_directories(JSSpecCompiler PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_options(JSSpecCompiler PRIVATE -Wno-missing-field-initializers)
