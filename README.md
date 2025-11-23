#Heading 1
<center>
Reproducing a Core Single-Cell RNA-Seq Analysis Pipeline Using Scanpy		
</center>

##Heading 2	
**Bold text**
Purpose:
###Heading 3
I replicated the Scanpy pipeline in order to annotate cells from a mystery single cell dataset, labeled as ‘bone marrow’, and to speculate whether ‘bone marrow’ is indeed the tissue of origin.

##Heading 2     
**Bold text**
Workflow:

The standard Scanpy pipeline using Jupyter notebook: 
    1. Install and import necessary libraries(Scanpy, anndata, Decoupler, Pandas)
    2. Data import and formatting
    3. Quality Control 
        ◦ %MT(mitochondrial genes), %RB(Ribosomal genes), %HB(Red blood cells/erythrocytes)
        ◦ gene counts per cell, total counts
    4. Filtering out low quality cells
        ◦ stresssed or irrelevant cells (%mt < 5, %RB < 10, and %HB <5)
        ◦ empty wells or doublets (gene_counts > 200 per cell  and cell_count >20 per gene)
    5. Finding Highly Variable Features 
    6. Dimensionality Reduction using PCA
    7. UMAP and leiden clustering
    8. Cell annotation using Decoupler and PanglaoDB
        ◦ Use top scoring cell per cluster for annotation
    9. Visualization of cell annotation(heatmap, dotplot, violinplot)

##Heading 2     
**Bold text**
Findings:

###Heading 3
Several populations of blood cells were identified in the dataset:

    • Neutrophils- Innate immune cells that are usually the first line of defense against infection function thru phagocytosis, or extracellular traps.
    • Gamma delta T cells- An alternative type of T lymphocytes that bridges innate and adaptive immunity to help fight infections or cancer.
    • Nuocytes- A type of innate lymphoid cell that plays a role in antibody or b cell  mediated immunity against parasites and allergens or tissue repair through cytokine production.
    • NK cells- Innate lymphocytes that destroy virus infected and cancer cells through the release of cytotoxic molecules that act on the target cells.
    • Naive B cells- Inactive B lymphocytes that are precursor to plasma cells or memory B cells­ and not exposed to activating antigen signals.
    • Platelets- Fragments of megakaryocyte cells that help with blood clotting and prevention of bleeding.
    • Plasma cells- Activated B lymphocytes that serve as antibody factories to help fight off infections from bacteria or viruses.
    • Monocytes-Circulating immune cells that help perform phagocytosis, antigen presentation and other functions to inhibit … They can differentiate into macrophages or dendritic cells upon entering tissues.

##Heading 2     
**Bold text**
Conclusion:
###Heading 3

The tissue of origin is most likely not bone marrow (most likely the lung or blood), considering the high composition of immune cells in the sample and absence of stem or progenitor mesenchymal or hematopoietic populations. The tissue could be undergoing early stage of infection or immune activation due to the presence of mostly innate immune cell types. Innate immune cells are the first types of cells to encounter pathogens or abnormal cells. 
It was surprising to see many of the genes overlapping between a lot, but not all, cell populations. It could be due to the inability of single cell sequencing in differentiating similar cell populations due to low sequencing depth. Alternatively, the markers used for annotation may not be specific enough, making automated annotation less than optimal and conclusions less solid.­

###Heading 3
**Bold**     
Packages installed  in the VSCODE conda environment:

###Heading 3
# Name                           Version          Build                    Channel
_libgcc_mutex                    0.1              conda_forge              conda-forge
_openmp_mutex                    4.5              2_gnu                    conda-forge
absl-py                          2.3.1            pypi_0                   pypi
adjusttext                       1.3.0            pypi_0                   pypi
aiofiles                         25.1.0           pypi_0                   pypi
aiohappyeyeballs                 2.6.1            pypi_0                   pypi
aiohttp                          3.13.2           pypi_0                   pypi
aiosignal                        1.4.0            pypi_0                   pypi
anndata                          0.11.4           pyhd8ed1ab_0             conda-forge
anyio                            4.11.0           pyhcf101f3_0             conda-forge
argon2-cffi                      25.1.0           pyhd8ed1ab_0             conda-forge
argon2-cffi-bindings             25.1.0           py310h7c4b9e2_2          conda-forge
array-api-compat                 1.12.0           pyhe01879c_0             conda-forge
arrow                            1.4.0            pyhcf101f3_0             conda-forge
asttokens                        3.0.0            pyhd8ed1ab_1             conda-forge
async-lru                        2.0.5            pyh29332c3_0             conda-forge
async-timeout                    5.0.1            pypi_0                   pypi
attrs                            25.4.0           pyh71513ae_0             conda-forge
babel                            2.17.0           pyhd8ed1ab_0             conda-forge
beautifulsoup4                   4.14.2           pyha770c72_0             conda-forge
bleach                           6.2.0            pyh29332c3_4             conda-forge
bleach-with-css                  6.2.0            h82add2a_4               conda-forge
blitzgsea                        1.3.54           pypi_0                   pypi
brotli                           1.2.0            h41a2e66_0               conda-forge
brotli-bin                       1.2.0            hf2c8021_0               conda-forge
brotli-python                    1.2.0            py310h8cfb67f_0          conda-forge
bzip2                            1.0.8            hda65f42_8               conda-forge
c-ares                           1.34.5           hb9d3cd8_0               conda-forge
ca-certificates                  2025.11.12       hbd8a1cb_0               conda-forge
cached-property                  1.5.2            hd8ed1ab_1               conda-forge
cached_property                  1.5.2            pyha770c72_1             conda-forge
celltypist                       1.7.1            pypi_0                   pypi
certifi                          2025.11.12       pyhd8ed1ab_0             conda-forge
cffi                             2.0.0            py310he7384ee_1          conda-forge
charset-normalizer               3.4.4            pyhd8ed1ab_0             conda-forge
chex                             0.1.90           pypi_0                   pypi
click                            8.3.0            pypi_0                   pypi
colorama                         0.4.6            pyhd8ed1ab_1             conda-forge
comm                             0.2.3            pyhe01879c_0             conda-forge
contourpy                        1.3.2            py310h3788b33_0          conda-forge
cycler                           0.12.1           pyhd8ed1ab_1             conda-forge
debugpy                          1.8.17           py310h25320af_0          conda-forge
decorator                        5.2.1            pyhd8ed1ab_0             conda-forge
decoupler                        2.1.2            pypi_0                   pypi
defusedxml                       0.7.1            pyhd8ed1ab_0             conda-forge
docrep                           0.3.2            pypi_0                   pypi
equinox                          0.13.2           pypi_0                   pypi
et-xmlfile                       2.0.0            pypi_0                   pypi
etils                            1.13.0           pypi_0                   pypi
exceptiongroup                   1.3.0            pyhd8ed1ab_0             conda-forge
executing                        2.2.1            pyhd8ed1ab_0             conda-forge
fa2-modified                     0.4              pypi_0                   pypi
filelock                         3.20.0           pypi_0                   pypi
flax                             0.10.7           pypi_0                   pypi
fonttools                        4.60.1           py310h3406613_0          conda-forge
fqdn                             1.5.1            pyhd8ed1ab_1             conda-forge
freetype                         2.14.1           ha770c72_0               conda-forge
frozenlist                       1.8.0            pypi_0                   pypi
fsspec                           2025.10.0        pypi_0                   pypi
grpcio                           1.76.0           pypi_0                   pypi
h11                              0.16.0           pyhd8ed1ab_0             conda-forge
h2                               4.3.0            pyhcf101f3_0             conda-forge
h5py                             3.15.1           nompi_py310h4aa865e_100  conda-forge
hdf5                             1.14.6           nompi_h6e4c0c1_103       conda-forge
hpack                            4.1.0            pyhd8ed1ab_0             conda-forge
httpcore                         1.0.9            pyh29332c3_0             conda-forge
httpx                            0.28.1           pyhd8ed1ab_0             conda-forge
humanize                         4.14.0           pypi_0                   pypi
hyperframe                       6.1.0            pyhd8ed1ab_0             conda-forge
icu                              75.1             he02047a_0               conda-forge
idna                             3.11             pyhd8ed1ab_0             conda-forge
igraph                           1.0.0            pypi_0                   pypi
imageio                          2.37.2           py310h7040dfc_0
importlib-metadata               8.7.0            pyhe01879c_1             conda-forge
importlib-resources              6.5.2            pypi_0                   pypi
ipykernel                        7.1.0            pyha191276_0             conda-forge
ipython                          8.37.0           pyh8f84b5b_0             conda-forge
isoduration                      20.11.0          pyhd8ed1ab_1             conda-forge
jax                              0.6.2            pypi_0                   pypi
jaxlib                           0.6.2            pypi_0                   pypi
jaxopt                           0.8.5            pypi_0                   pypi
jaxtyping                        0.3.3            pypi_0                   pypi
jedi                             0.19.2           pyhd8ed1ab_1             conda-forge
jinja2                           3.1.6            pyhd8ed1ab_0             conda-forge
joblib                           1.5.2            pyhd8ed1ab_0             conda-forge
json5                            0.12.1           pyhd8ed1ab_0             conda-forge
jsonpointer                      3.0.0            py310hff52083_2          conda-forge
jsonschema                       4.25.1           pyhe01879c_0             conda-forge
jsonschema-specifications        2025.9.1         pyhcf101f3_0             conda-forge
jsonschema-with-format-nongpl    4.25.1           he01879c_0               conda-forge
jupyter-lsp                      2.3.0            pyhcf101f3_0             conda-forge
jupyter_client                   8.6.3            pyhd8ed1ab_1             conda-forge
jupyter_core                     5.9.1            pyhc90fa1f_0             conda-forge
jupyter_events                   0.12.0           pyh29332c3_0             conda-forge
jupyter_server                   2.17.0           pyhcf101f3_0             conda-forge
jupyter_server_terminals         0.5.3            pyhd8ed1ab_1             conda-forge
jupyterlab                       4.4.10           pyhd8ed1ab_0             conda-forge
jupyterlab_pygments              0.3.0            pyhd8ed1ab_2             conda-forge
jupyterlab_server                2.28.0           pyhcf101f3_0             conda-forge
keyutils                         1.6.3            hb9d3cd8_0               conda-forge
kiwisolver                       1.4.9            py310haaf941d_2          conda-forge
krb5                             1.21.3           h659f571_0               conda-forge
lamin-utils                      0.15.0           pypi_0                   pypi
lark                             1.3.1            pyhd8ed1ab_0             conda-forge
lazy_loader                      0.4              py310h06a4308_0
lcms2                            2.17             h717163a_0               conda-forge
ld_impl_linux-64                 2.44             h1aa0949_5               conda-forge
legacy-api-wrap                  1.5              pyhd8ed1ab_0             conda-forge
legendkit                        0.3.6            pypi_0                   pypi
leidenalg                        0.11.0           pypi_0                   pypi
lerc                             4.0.0            h0aef613_1               conda-forge
libaec                           1.1.4            h3f801dc_0               conda-forge
libblas                          3.9.0            38_h4a7cf45_openblas     conda-forge
libbrotlicommon                  1.2.0            h09219d5_0               conda-forge
libbrotlidec                     1.2.0            hd53d788_0               conda-forge
libbrotlienc                     1.2.0            h02bd7ab_0               conda-forge
libcblas                         3.9.0            38_h0358290_openblas     conda-forge
libcurl                          8.17.0           h4e3cde8_0               conda-forge
libdeflate                       1.25             h17f619e_0               conda-forge
libedit                          3.1.20250104     pl5321h7949ede_0         conda-forge
libev                            4.33             hd590300_2               conda-forge
libexpat                         2.7.1            hecca717_0               conda-forge
libffi                           3.5.2            h9ec8514_0               conda-forge
libfreetype                      2.14.1           ha770c72_0               conda-forge
libfreetype6                     2.14.1           h73754d4_0               conda-forge
libgcc                           15.2.0           h767d61c_7               conda-forge
libgcc-ng                        15.2.0           h69a702a_7               conda-forge
libgfortran                      15.2.0           h69a702a_7               conda-forge
libgfortran5                     15.2.0           hcd61629_7               conda-forge
libgomp                          15.2.0           h767d61c_7               conda-forge
libhwloc                         2.12.1           default_h7f8ec31_1002    conda-forge
libiconv                         1.18             h3b78370_2               conda-forge
libjpeg-turbo                    3.1.2            hb03c661_0               conda-forge
liblapack                        3.9.0            38_h47877c9_openblas     conda-forge
liblzma                          5.8.1            hb9d3cd8_2               conda-forge
libnghttp2                       1.67.0           had1ee68_0               conda-forge
libnsl                           2.0.1            hb9d3cd8_1               conda-forge
libopenblas                      0.3.30           pthreads_h94d23a6_3      conda-forge
libpng                           1.6.50           h421ea60_1               conda-forge
libsodium                        1.0.20           h4ab18f5_0               conda-forge
libsqlite                        3.51.0           hee844dc_0               conda-forge
libssh2                          1.11.1           hcf80075_0               conda-forge
libstdcxx                        15.2.0           h8f9b012_7               conda-forge
libstdcxx-ng                     15.2.0           h4852527_7               conda-forge
libtiff                          4.7.1            h9d88235_1               conda-forge
libuuid                          2.41.2           he9a06e4_0               conda-forge
libwebp-base                     1.6.0            hd42ef1d_0               conda-forge
libxcb                           1.17.0           h8a09558_0               conda-forge
libxcrypt                        4.4.36           hd590300_1               conda-forge
libxml2                          2.15.1           h26afc86_0               conda-forge
libxml2-16                       2.15.1           ha9997c6_0               conda-forge
libzlib                          1.3.1            hb9d3cd8_2               conda-forge
lightning                        2.5.6            pypi_0                   pypi
lightning-utilities              0.15.2           pypi_0                   pypi
lineax                           0.0.8            pypi_0                   pypi
llvmlite                         0.45.1           py310hee1c697_0          conda-forge
markdown                         3.10             pypi_0                   pypi
markdown-it-py                   4.0.0            pypi_0                   pypi
markupsafe                       3.0.3            py310h3406613_0          conda-forge
marsilea                         0.5.6            pypi_0                   pypi
matplotlib-base                  3.10.7           py310hfde16b3_0          conda-forge
matplotlib-inline                0.2.1            pyhd8ed1ab_0             conda-forge
mdurl                            0.1.2            pypi_0                   pypi
mistune                          3.1.4            pyhcf101f3_0             conda-forge
ml-collections                   1.1.0            pypi_0                   pypi
ml-dtypes                        0.5.4            pypi_0                   pypi
mpmath                           1.3.0            pypi_0                   pypi
msgpack                          1.1.2            pypi_0                   pypi
mudata                           0.3.2            pypi_0                   pypi
multidict                        6.7.0            pypi_0                   pypi
multipledispatch                 1.0.0            pypi_0                   pypi
munkres                          1.1.4            pyhd8ed1ab_1             conda-forge
muon                             0.1.7            pypi_0                   pypi
natsort                          8.4.0            pyh29332c3_1             conda-forge
nbclient                         0.10.2           pyhd8ed1ab_0             conda-forge
nbconvert-core                   7.16.6           pyhcf101f3_1             conda-forge
nbformat                         5.10.4           pyhd8ed1ab_1             conda-forge
ncurses                          6.5              h2d0b736_3               conda-forge
nest-asyncio                     1.6.0            pyhd8ed1ab_1             conda-forge
networkx                         3.4.2            pyh267e887_2             conda-forge
notebook-shim                    0.2.4            pyhd8ed1ab_1             conda-forge
numba                            0.62.1           py310h3477d8a_0          conda-forge
numpy                            2.2.6            py310hefbff90_0          conda-forge
numpyro                          0.19.0           pypi_0                   pypi
nvidia-cublas-cu12               12.8.4.1         pypi_0                   pypi
nvidia-cuda-cupti-cu12           12.8.90          pypi_0                   pypi
nvidia-cuda-nvrtc-cu12           12.8.93          pypi_0                   pypi
nvidia-cuda-runtime-cu12         12.8.90          pypi_0                   pypi
nvidia-cudnn-cu12                9.10.2.21        pypi_0                   pypi
nvidia-cufft-cu12                11.3.3.83        pypi_0                   pypi
nvidia-cufile-cu12               1.13.1.3         pypi_0                   pypi
nvidia-curand-cu12               10.3.9.90        pypi_0                   pypi
nvidia-cusolver-cu12             11.7.3.90        pypi_0                   pypi
nvidia-cusparse-cu12             12.5.8.93        pypi_0                   pypi
nvidia-cusparselt-cu12           0.7.1            pypi_0                   pypi
nvidia-nccl-cu12                 2.27.5           pypi_0                   pypi
nvidia-nvjitlink-cu12            12.8.93          pypi_0                   pypi
nvidia-nvshmem-cu12              3.3.20           pypi_0                   pypi
nvidia-nvtx-cu12                 12.8.90          pypi_0                   pypi
openjpeg                         2.5.4            h55fea9a_0               conda-forge
openpyxl                         3.1.5            pypi_0                   pypi
openssl                          3.6.0            h26f9b46_0               conda-forge
opt-einsum                       3.4.0            pypi_0                   pypi
optax                            0.2.6            pypi_0                   pypi
orbax-checkpoint                 0.11.28          pypi_0                   pypi
ott-jax                          0.6.0            pypi_0                   pypi
overrides                        7.7.0            pyhd8ed1ab_1             conda-forge
packaging                        25.0             pyh29332c3_1             conda-forge
pandas                           2.3.3            py310h0158d43_1          conda-forge
pandocfilters                    1.5.0            pyhd8ed1ab_0             conda-forge
parso                            0.8.5            pyhcf101f3_0             conda-forge
patsy                            1.0.2            pyhcf101f3_0             conda-forge
pertpy                           0.10.0           pypi_0                   pypi
pexpect                          4.9.0            pyhd8ed1ab_1             conda-forge
pickleshare                      0.7.5            pyhd8ed1ab_1004          conda-forge
pillow                           12.0.0           py310h80abafc_0          conda-forge
pip                              25.3             pyh8b19718_0             conda-forge
platformdirs                     4.5.0            pyhcf101f3_0             conda-forge
ply                              3.11             pypi_0                   pypi
prometheus_client                0.23.1           pyhd8ed1ab_0             conda-forge
prompt-toolkit                   3.0.52           pyha770c72_0             conda-forge
propcache                        0.4.1            pypi_0                   pypi
protobuf                         6.33.1           pypi_0                   pypi
psutil                           7.1.3            py310h139afa4_0          conda-forge
pthread-stubs                    0.4              hb9d3cd8_1002            conda-forge
ptyprocess                       0.7.0            pyhd8ed1ab_1             conda-forge
pubchempy                        1.0.5            pypi_0                   pypi
pure_eval                        0.2.3            pyhd8ed1ab_1             conda-forge
pyarrow                          22.0.0           pypi_0                   pypi
pycparser                        2.22             pyh29332c3_1             conda-forge
pygments                         2.19.2           pyhd8ed1ab_0             conda-forge
pynndescent                      0.5.13           pyhd8ed1ab_1             conda-forge
pyomo                            6.9.5            pypi_0                   pypi
pyparsing                        3.2.5            pyhcf101f3_0             conda-forge
pyro-api                         0.1.2            pypi_0                   pypi
pyro-ppl                         1.9.1            pypi_0                   pypi
pysocks                          1.7.1            pyha55dd90_7             conda-forge
python                           3.10.19          h3c07f61_2_cpython       conda-forge
python-dateutil                  2.9.0.post0      pyhe01879c_2             conda-forge
python-fastjsonschema            2.21.2           pyhe01879c_0             conda-forge
python-json-logger               2.0.7            pyhd8ed1ab_0             conda-forge
python-tzdata                    2025.2           pyhd8ed1ab_0             conda-forge
python_abi                       3.10             8_cp310                  conda-forge
pytorch-lightning                2.5.6            pypi_0                   pypi
pytz                             2025.2           pyhd8ed1ab_0             conda-forge
pyyaml                           6.0.3            py310h3406613_0          conda-forge
pyzmq                            27.1.0           py310h4f33d48_0          conda-forge
qhull                            2020.2           h434a139_5               conda-forge
readline                         8.2              h8c095d6_2               conda-forge
referencing                      0.37.0           pyhcf101f3_0             conda-forge
requests                         2.32.5           pyhd8ed1ab_0             conda-forge
rfc3339-validator                0.1.4            pyhd8ed1ab_1             conda-forge
rfc3986-validator                0.1.1            pyh9f0ad1d_0             conda-forge
rfc3987-syntax                   1.1.0            pyhe01879c_1             conda-forge
rich                             14.2.0           pypi_0                   pypi
rpds-py                          0.28.0           py310hd8f68c5_1          conda-forge
scanpy                           1.11.5           pyhd8ed1ab_0             conda-forge
scikit-image                     0.25.2           py310hc74f9fe_0
scikit-learn                     1.7.2            py310h228f341_0          conda-forge
scikit-misc                      0.5.2            pypi_0                   pypi
scipy                            1.15.2           py310h1d65ade_0          conda-forge
scvi-tools                       1.3.3            pypi_0                   pypi
seaborn                          0.13.2           hd8ed1ab_3               conda-forge
seaborn-base                     0.13.2           pyhd8ed1ab_3             conda-forge
send2trash                       1.8.3            pyh0d859eb_1             conda-forge
session-info2                    0.2.3            pyhd8ed1ab_0             conda-forge
setuptools                       80.9.0           pyhff2d567_0             conda-forge
simplejson                       3.20.2           pypi_0                   pypi
six                              1.17.0           pyhe01879c_1             conda-forge
sniffio                          1.3.1            pyhd8ed1ab_2             conda-forge
soupsieve                        2.8              pyhd8ed1ab_0             conda-forge
sparse                           0.17.0           pypi_0                   pypi
sparsecca                        0.3.1            pypi_0                   pypi
stack_data                       0.6.3            pyhd8ed1ab_1             conda-forge
statsmodels                      0.14.5           py310hf779ad0_1          conda-forge
sympy                            1.14.0           pypi_0                   pypi
tbb                              2022.3.0         h8d10470_1               conda-forge
tensorboard                      2.20.0           pypi_0                   pypi
tensorboard-data-server          0.7.2            pypi_0                   pypi
tensorstore                      0.1.78           pypi_0                   pypi
terminado                        0.18.1           pyh0d859eb_0             conda-forge
texttable                        1.7.0            pypi_0                   pypi
threadpoolctl                    3.6.0            pyhecae5ae_0             conda-forge
tifffile                         2025.2.18        py310h06a4308_0
tinycss2                         1.4.0            pyhd8ed1ab_0             conda-forge
tk                               8.6.13           noxft_hd72426e_102       conda-forge
tomli                            2.3.0            pyhcf101f3_0             conda-forge
toolz                            1.1.0            pypi_0                   pypi
torch                            2.9.1            pypi_0                   pypi
torchmetrics                     1.8.2            pypi_0                   pypi
tornado                          6.5.2            py310h7c4b9e2_2          conda-forge
tqdm                             4.67.1           pyhd8ed1ab_1             conda-forge
traitlets                        5.14.3           pyhd8ed1ab_1             conda-forge
treescope                        0.1.10           pypi_0                   pypi
triton                           3.5.1            pypi_0                   pypi
typing-extensions                4.15.0           h396c80c_0               conda-forge
typing_extensions                4.15.0           pyhcf101f3_0             conda-forge
typing_utils                     0.1.0            pyhd8ed1ab_1             conda-forge
tzdata                           2025b            h78e105d_0               conda-forge
umap-learn                       0.5.9.post2      py310hff52083_0          conda-forge
unicodedata2                     17.0.0           py310h7c4b9e2_0          conda-forge
uri-template                     1.3.0            pyhd8ed1ab_1             conda-forge
urllib3                          2.5.0            pyhd8ed1ab_0             conda-forge
wadler-lindig                    0.1.7            pypi_0                   pypi
wcwidth                          0.2.14           pyhd8ed1ab_0             conda-forge
webcolors                        25.10.0          pyhd8ed1ab_0             conda-forge
webencodings                     0.5.1            pyhd8ed1ab_3             conda-forge
websocket-client                 1.9.0            pyhd8ed1ab_0             conda-forge
werkzeug                         3.1.3            pypi_0                   pypi
wheel                            0.45.1           pyhd8ed1ab_1             conda-forge
xarray                           2025.6.1         pypi_0                   pypi
xorg-libxau                      1.0.12           hb03c661_1               conda-forge
xorg-libxdmcp                    1.1.5            hb03c661_1               conda-forge
yaml                             0.2.5            h280c20c_3               conda-forge
yarl                             1.22.0           pypi_0                   pypi
zeromq                           4.3.5            h387f397_9               conda-forge
zipp                             3.23.0           pyhd8ed1ab_0             conda-forge
zlib-ng                          2.2.5            hde8ca8f_0               conda-forge
zstandard                        0.25.0           py310h139afa4_1          conda-forge
zstd                             1.5.7            hb8e6e7a_2               conda-forge
