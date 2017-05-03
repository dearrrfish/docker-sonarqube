FROM sonarqube:latest

MAINTAINER Yu Jin "dearrrfish@gmail.com"

RUN mkdir -p $HOME/sonar-plugins

# Databse
ENV SONARQUBE_JDBC_URL jdbc:mysql://localhost:3306/sonar?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance

# Plugins

ENV SWIFT_PLUGIN_VERSION 0.3.4
RUN set -x && curl -sLo $HOME/sonar-plugins/backelite-sonar-swift-plugin-${SWIFT_PLUGIN_VERSION}.jar \
	https://github.com/Backelite/sonar-swift/releases/download/${SWIFT_PLUGIN_VERSION}/backelite-sonar-swift-plugin-${SWIFT_PLUGIN_VERSION}.jar

ENV OBJECTIVE_C_PLUGIN_VERSION 0.6.1
RUN set -x && curl -sLo $HOME/sonar-plugins/backelite-sonar-objective-c-plugin-${OBJECTIVE_C_PLUGIN_VERSION}.jar \
	https://github.com/Backelite/sonar-objective-c/releases/download/${OBJECTIVE_C_PLUGIN_VERSION}/backelite-sonar-objective-c-plugin-${OBJECTIVE_C_PLUGIN_VERSION}.jar

ENV ANDROID_LINT_PLUGIN_VERSION 1.1
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-android-plugin-${ANDROID_LINT_PLUGIN_VERSION}.jar \
	https://github.com/SonarQubeCommunity/sonar-android/releases/download/${ANDROID_LINT_PLUGIN_VERSION}/sonar-android-plugin-${ANDROID_LINT_PLUGIN_VERSION}.jar

ENV JAVA_PLUGIN_VERSION 4.8.0.9441
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-java-plugin-${JAVA_PLUGIN_VERSION}.jar \
	https://sonarsource.bintray.com/Distribution/sonar-java-plugin/sonar-java-plugin-${JAVA_PLUGIN_VERSION}.jar

ENV FINDBUGS_PLUGIN_VERSION 3.4.4
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-findbugs-plugin-${FINDBUGS_PLUGIN_VERSION}.jar \
  https://github.com/SonarQubeCommunity/sonar-findbugs/releases/download/${FINDBUGS_PLUGIN_VERSION}/sonar-findbugs-plugin-${FINDBUGS_PLUGIN_VERSION}.jar

ENV JS_PLUGIN_VERSION 3.0.0.4962
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-javascript-plugin-${JS_PLUGIN_VERSION}.jar \
	https://sonarsource.bintray.com/Distribution/sonar-javascript-plugin/sonar-javascript-plugin-${JS_PLUGIN_VERSION}.jar

ENV PHP_PLUGIN_VERSION 2.9.2.1744
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-php-plugin-${PHP_PLUGIN_VERSION}.jar \
  https://sonarsource.bintray.com/Distribution/sonar-php-plugin/sonar-php-plugin-${PHP_PLUGIN_VERSION}.jar

ENV PYTHON_PLUGIN_VERSION 1.7.0.1195
RUN set -x && curl -sLo $HOME/sonar-plugins/sonar-python-plugin-${PYTHON_PLUGIN_VERSION}.jar \
  https://sonarsource.bintray.com/Distribution/sonar-python-plugin/sonar-python-plugin-${PYTHON_PLUGIN_VERSION}.jar

# End Plugins

RUN cp $HOME/sonar-plugins/* $SONARQUBE_HOME/extensions/plugins
