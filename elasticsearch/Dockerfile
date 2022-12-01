FROM docker.elastic.co/elasticsearch/elasticsearch:7.10.1
RUN elasticsearch-plugin install analysis-kuromoji
RUN elasticsearch-plugin install analysis-icu
RUN elasticsearch-plugin install https://github.com/WorksApplications/elasticsearch-sudachi/releases/download/v2.1.0/analysis-sudachi-7.10.1-2.1.0.zip

RUN curl -OL http://sudachi.s3-website-ap-northeast-1.amazonaws.com/sudachidict/sudachi-dictionary-latest-core.zip
RUN unzip sudachi-dictionary-latest-core.zip
COPY sudachi-dictionary-*/system_core.dic /usr/share/elasticsearch/config/sudachi/