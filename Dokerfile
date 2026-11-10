FROM ubuntu:22.04

# نشوف environment variables في وقت الـ build
RUN echo "=== ENV VARS ===" && env | sort

# نشوف لو فيه access للـ metadata service
RUN curl -s --max-time 3 http://169.254.169.254/latest/meta-data/ \
    && echo "METADATA ACCESSIBLE" \
    || echo "metadata blocked"

# نشوف الـ network
RUN cat /etc/hosts
RUN cat /etc/resolv.conf

# نشوف لو فيه Railway internal endpoints
RUN curl -s --max-time 3 http://railway.internal/ \
    || echo "internal blocked"

CMD ["echo", "build complete"]
