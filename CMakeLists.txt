project(funchook C ASM)
cmake_minimum_required(VERSION 3.11)

add_library(funchook
  src/funchook.c
  src/funchook_io.c
  src/funchook_unix.c
  src/funchook_x86.c
  src/os_func.c
  src/os_func_unix.c
  src/funchook_syscall.S
  src/printf_base.c

	distorm/src/mnemonics.c
	distorm/src/wstring.c
	distorm/src/textdefs.c
	distorm/src/prefix.c
	distorm/src/operands.c
	distorm/src/insts.c
	distorm/src/instructions.c
	distorm/src/distorm.c
	distorm/src/decoder.c
)

target_include_directories(funchook
  PUBLIC include
  PRIVATE distorm/include
)

target_compile_options(funchook
  PRIVATE -D_GNU_SOURCE -fPIC
)
