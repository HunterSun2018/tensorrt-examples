# Train MNIST model
```
python3 mnist.py
```

# Build tensorRT application
```
cmake . -Bbuild -DCMAKE_CUDA_COMPILER=/usr/local/cuda/bin/nvcc
cd build && make
```

# Run inference by TensorRT
```
./test -d ../models
```