# for test only


    cd;cd test;
    wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/download/v1.5.2/monaco-linux-amd64;
    mv monaco-linux-amd64 monaco;
    chmod +x monaco;
    export NEW_CLI=1;
    ./monaco --version


    monaco deploy -e=environments.yaml test
