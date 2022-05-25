CFLAGS = -std=c++17 -O2
LDFLAGS = -lglfw -lvulkan -ldl -lpthread -lX11 -lXxf86vm -lXrandr -lXi

VulkanTest: main.cpp
	g++ $(CFLAGS) -o VulkanTest main.cpp $(LDFLAGS)

.PHONY: test clean

shader:
	glslc 09_shader_base.vert -o shaders/vert.spv
	glslc 09_shader_base.frag -o shaders/frag.spv

test: VulkanTest
	./VulkanTest

clean:
	rm -f VulkanTest
