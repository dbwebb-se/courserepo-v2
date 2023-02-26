FROM mcr.microsoft.com/dotnet/sdk

# Set the Environment Variable for the DOTNET CLI HOME PATH
ARG dotnet_cli_home_arg=/tmp/
ENV DOTNET_CLI_HOME=$dotnet_cli_home_arg

# Act as local user, not root, with workdir homedir
RUN groupadd -r dbw && useradd --no-log-init -r -g dbw dbw
WORKDIR /home/dbw
USER dbw
