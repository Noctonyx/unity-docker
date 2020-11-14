FROM noctonyx/unity-hub:1.0.1

# Install editor
ARG version="2020.2.0b11"
ARG changeSet="c499c2bf2e80"
RUN unity-hub install --version "$version" --changeset "$changeSet" | grep 'Error' | exit $(wc -l)