FROM mcr.microsoft.com/aifx/acpt/stable-ubuntu2204-cu126-py310-torch280:{{latest-image-tag:biweekly\.\d{6}\.\d{1}.*}}

USER root

COPY requirements.txt .
RUN pip install -r requirements.txt
RUN pip install --no-build-isolation git+https://github.com/facebookresearch/detectron2.git@a1ce2f9

# vulnerability in base conda env
RUN conda run -n base python -m pip install --upgrade urllib3==2.6.3 aiohttp==3.13.3 PyNaCl==1.6.2

# FROM mcr.microsoft.com/aifx/acpt/stable-ubuntu2204-cu126-py310-torch280:biweekly.202602.2


# USER root

# RUN apt-get update && \
#     DEBIAN_FRONTEND=noninteractive apt-get -y upgrade && \
#     apt-get clean && \
#     rm -rf /var/lib/apt/lists/*

# COPY requirements.txt .
# RUN pip install -r requirements.txt
# # Install the local azureml-acft-image-components wheel (includes olympus_biomed_parse_3d)
# COPY azureml_acft_image_components-0.1.0.0-py3-none-any.whl /tmp/
# RUN pip install /tmp/azureml_acft_image_components-0.1.0.0-py3-none-any.whl[mip3d] && \
#     rm /tmp/azureml_acft_image_components-0.1.0.0-py3-none-any.whl


# RUN pip install --no-build-isolation git+https://github.com/facebookresearch/detectron2.git@a1ce2f9

# # vulnerability in base conda env
# RUN conda run -n base python -m pip install --upgrade urllib3==2.6.3 aiohttp==3.13.3 PyNaCl==1.6.2

# # setuptools >=71 dropped pkg_resources; mlflow-skinny 2.13.2 still imports it.
# # Pin setuptools <71 LAST so nothing can evict it.
# RUN pip install --upgrade pip==26.0 wheel==0.46.2 "setuptools<71"