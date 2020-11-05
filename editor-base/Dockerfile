FROM noctonyx/unity-hub:1.0.0

# Install editor
ARG version="2020.2.0b9"
ARG changeSet="ef2968fa77ae"
RUN unity-hub install --version "$version" --changeset "$changeSet" | grep 'Error' | exit $(wc -l)