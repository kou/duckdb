

.PHONY: duckdb clean main pkg-config

all: duckdb main

clean:
	rm -rf build
	rm -rf build-pkg-config

duckdb:
	cd ../.. && make

main:
	mkdir -p build
	cd build && cmake .. && make
	build/example

pkg-config:
	mkdir -p build-pkg-config
	$(CXX) -o build-pkg-config/example main.cpp $$(pkgconf --cflags --libs duckdb)
	build-pkg-config/example
