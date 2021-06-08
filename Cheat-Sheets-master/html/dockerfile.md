;

Reference
---------

{: .-three-column}

### Inheritance

    FROM ruby:2.2.2

### Variables

    ENV APP_HOME /myapp
    RUN mkdir $APP_HOME

    ARG APP_HOME=""
    RUN mkdir $APP_HOME

### Initialization

    RUN bundle install

    WORKDIR /myapp

    VOLUME ["/data"]
    # Specification for mount point

    ADD file.xyz /file.xyz
    COPY --chown=user:group host_file.xyz /path/container_file.xyz

### Onbuild

    ONBUILD RUN bundle install
    # when used with another file

### Commands

    EXPOSE 5900
    CMD    ["bundle", "exec", "rails", "server"]

### Entrypoint

    ENTRYPOINT ["executable", "param1", "param2"]
    ENTRYPOINT command param1 param2

Configures a container that will run as an executable.

    ENTRYPOINT exec top -b

This will use shell processing to substitute shell variables, and will ignore any `CMD` or `docker run` command line arguments.

### Metadata

    LABEL version="1.0"

    LABEL "com.example.vendor"="ACME Incorporated"
    LABEL com.example.label-with-value="foo"

    LABEL description="This text illustrates \
    that label-values can span multiple lines."

See also
--------

{: .-one-column}

-   <a href="https://docs.docker.com/engine/reference/builder/" class="uri">https://docs.docker.com/engine/reference/builder/</a>
