
FROM quay.io/pypa/manylinux1_x86_64

# Install Cmake (either from source (reliable) or from yum (64-bit only, and it doesn't symlink in a cmake executable))
# ALTERNATE: RUN yum install -y cmake28 && ln -s `which cmake28` /usr/local/bin/cmake
RUN wget --no-check-certificate http://www.cmake.org/files/v2.8/cmake-2.8.10.2.tar.gz && tar -zxvf cmake-2.8.10.2.tar.gz && cd cmake-2.8.10.2 && ./bootstrap && make && make install

# Install virtualenv into one of the python installations for creating other virtual environments
RUN /opt/python/cp27-cp27m/bin/pip install virtualenv

# Create virtual environments
RUN /opt/python/cp27-cp27m/bin/virtualenv /py27 --python=/opt/python/cp27-cp27m/bin/python
RUN /opt/python/cp27-cp27m/bin/virtualenv /py27mu --python=/opt/python/cp27-cp27mu/bin/python
RUN /opt/python/cp27-cp27m/bin/virtualenv /py33 --python=/opt/python/cp33-cp33m/bin/python
RUN /opt/python/cp27-cp27m/bin/virtualenv /py34 --python=/opt/python/cp34-cp34m/bin/python
RUN /opt/python/cp27-cp27m/bin/virtualenv /py35 --python=/opt/python/cp35-cp35m/bin/python

# Install pip packages needed
RUN /py27/bin/pip install cython
RUN /py27mu/bin/pip install cython
RUN /py33/bin/pip install cython
RUN /py34/bin/pip install cython
RUN /py35/bin/pip install cython