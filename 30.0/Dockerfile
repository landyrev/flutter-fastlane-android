FROM cimg/android:30.0
ENV PATH="/usr/local/bin/flutter/bin:${PATH}"
# Install and pre-cache Flutter.
USER root
RUN curl -o flutter.tar.xz https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_2.2.3-stable.tar.xz && \
  tar xf flutter.tar.xz -C /usr/local/bin && \
  rm flutter.tar.xz

RUN /usr/local/bin/flutter/bin/flutter precache --no-web --no-linux --no-windows --no-fuchsia --no-ios --no-macos
RUN apt update
RUN apt install -y ruby ruby-dev rubygems
# Install fastlane.
RUN gem install fastlane -NV
ENV PATH="/usr/local/gradle-6.8.3/bin:${PATH}"