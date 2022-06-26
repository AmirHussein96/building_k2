# Building_k2 on QCRI cluster

1. Reserve a node with a GPU
2. cd k2
3. mkdir build
4. cd build
5. Source `../activate-cuda-10.2.sh`
6. run `cmake   -DCUDNN_LIBRARY_PATH=/cm/shared/apps/cudnn8.0-cuda10.2/8.0.5.39/lib64/libcudnn.so   -DCUDNN_INCLUDE_PATH=/cm/shared/apps/cudnn8.0-cuda10.2/8.0.5.39/include   -DCMAKE_BUILD_TYPE=Release   .. &> log`
7. make -j 
8. export PYTHONPATH=$PWD/../k2/python:$PWD/lib:$PYTHONPATH
9. python3 -c "import k2" 

Check the issue here https://github.com/k2-fsa/k2/issues/952 
