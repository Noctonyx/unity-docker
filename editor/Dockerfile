FROM noctonyx/editor-base:2020.2.0b9 AS builder

# Install modules for that editor
RUN      unity-hub install-modules --version "2020.2.0b9" --module "windows-mono" --childModules | grep 'Missing module' | exit $(wc -l) 

FROM noctonyx/unity-base:1.0.0

# Always put "Editor" and "modules.json" directly in $UNITY_PATH
ARG version="2020.2.0b9"
COPY --from=builder /opt/unity/editors/$version/ "$UNITY_PATH/"

# Add a file containing the version for this build
RUN echo $version > "$UNITY_PATH/version"

# Alias to "unity-editor" with default params
RUN echo '#!/bin/bash\nxvfb-run -ae /dev/stdout "$UNITY_PATH/Editor/Unity" -batchmode "$@"' > /usr/bin/unity-editor \
 && chmod +x /usr/bin/unity-editor
ENV UNITY_VERSION=$version
