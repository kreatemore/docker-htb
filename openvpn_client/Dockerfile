FROM alpine:latest
RUN apk --no-cache add 	openvpn

RUN mkdir /usr/share/openvpn
RUN cp /etc/openvpn/* /usr/share/openvpn/

WORKDIR /etc/openvpn
ENTRYPOINT ["openvpn"]

# Change this to your ovpn file
CMD ["0xdevice.ovpn"]
