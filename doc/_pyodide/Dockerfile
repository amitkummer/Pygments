FROM ghcr.io/pyodide/pyodide:0.20.0 AS build-stage

WORKDIR pyodide

# copy new meta with path instead of pypi url
COPY doc/_pyodide/meta.yaml packages/Pygments/ 

COPY . /pygments

ENV PYODIDE_PACKAGES=Pygments 

RUN make

FROM scratch AS export-stage

COPY --from=build-stage /src/pyodide/build /
