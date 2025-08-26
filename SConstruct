env = Environment(tools = ['mingw'])
env['CC'] = 'clang'
env['CXX'] = 'clang++'

env['ENV']['PATH'] = ['C:/reirina/llvm-mingw-20250812-ucrt-x86_64/bin']
env.Append(CPPPATH = ['../SDLdeps/include'])
env.Append(LIBPATH = ['../SDLdeps/lib'])

# # To use dynamic link, need to copy SDL3.dll side by side with .exe to execute
# env.Append(CPPPATH = ['../SDL3-3.2.20/x86_64-w64-mingw32/include'])
# env.Append(LIBPATH = ['../SDL3-3.2.20/x86_64-w64-mingw32/lib'])

# libSDL3 = File('../SDLdeps/lib/libSDL3.a')
# env.Append(LIBS = [libSDL3])

# env.Append(LINKFLAGS = ['-static'])

env.Append(LIBS = ['SDL3'])

env.Program('snake.c')
