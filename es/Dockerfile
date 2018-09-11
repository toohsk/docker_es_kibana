FROM docker.elastic.co/elasticsearch/elasticsearch:6.4.0

# Install japanese analyzer
RUN echo "y" | elasticsearch-plugin install org.codelibs:elasticsearch-analysis-kuromoji-neologd:6.3.1
RUN echo "y" | elasticsearch-plugin install org.codelibs:elasticsearch-analysis-ja:6.3.1
