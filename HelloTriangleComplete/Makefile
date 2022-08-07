CFLAGS = -std=c++17 -O2
LDFLAGS = -lglfw -lvulkan -ldl -lpthread -lX11 -lXxf86vm -lXrandr -lXi
# HOMEBREW_DIR = /usr/local
HOMEBREW_DIR = ~/homebrew
MACFLAGS = -lglfw -lvulkan -ldl -I $(HOMEBREW_DIR)/include -L $(HOMEBREW_DIR)/lib -L /usr/local/lib -I /usr/local/include/

VulkanTest: main.cpp
	g++ $(CFLAGS) -o VulkanTest main.cpp $(LDFLAGS)

VulkanTestMac: main.cpp
	clang++ $(CFLAGS) -o VulkanTest main.cpp $(MACFLAGS)

.PHONY: test clean

shader:
	glslc 09_shader_base.vert -o shaders/vert.spv
	glslc 09_shader_base.frag -o shaders/frag.spv

test: VulkanTest
	./VulkanTest

clean:
	rm -f VulkanTest
