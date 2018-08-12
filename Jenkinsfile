#!groovy

stages = [

  [name: 'Checkout',
   body: stageCheckout,
   args:  ["http://gitlab.dmz/leighgarbs/netsuspend.git"]],

  [name: 'cppcheck',
   body: stageCppcheck,
   args: []],

  [name: 'Release Build',
   body: stageBuild,
   args: ['release', '']],

  [name: 'Debug Build',
   body: stageBuild,
   args: ['debug', '']],

  [name: 'Clang Static Analyzer',
   body: stageClangStaticAnalysis,
   args: []],

  [name: 'Detect GCC Warnings',
   body: stageDetectWarnings,
   args: ["GNU Make + GNU C Compiler (gcc)"]],

  [name: 'Detect Clang Warnings',
   body: stageDetectWarnings,
   args: ["Clang (LLVM based)"]]

]

doStages(stages)
