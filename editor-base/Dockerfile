FROM noctonyx/unity-hub:1.0.0

# Install editor
ARG version="2020.2.0b10"
ARG changeSet="19f63eee530c"
RUN unity-hub install --version "$version" --changeset "$changeSet" | grep 'Error' | exit $(wc -l)