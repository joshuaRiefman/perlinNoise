# perlinNoise
A Perlin noise generation library implemented in Go

## Build 

To build a shared library accessible from Python
```bash
go build -o perlin_noise.so -buildmode=c-shared main/src
```
You made need to include the following build flags
```bash
CGO_ENABLED=1
```
As well as operating and platform specific flags. For example on an Apple Silicon Mac,
```bash
GOOS=darwin GOARCH=arm64
```

## Tests and Examples
To run _perlinNoise_ and generate example simplex and Perlin noise images,
```bash
go run main/src
```
![Simplex Noise](example/output_simplex.png)  
![Perlin Noise](example/output_perlin.png)  
Or, you can run the Python test script that serves as a demo of how to integrate _perlinNoise_ into your project.
Ensure you have the required dependencies:
```bash
python3 --version
pip3 --version
pip3 install -r requirements.txt
```
To run the script,
```bash
python3 test.py
```

## Output 
_perlinNoise_ currently outputs a `256x256` matrix of noise of which the values range from `0.0` to `1.0`. Capacity to control dimensions is under development.