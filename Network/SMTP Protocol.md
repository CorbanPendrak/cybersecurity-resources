#network 
[[Network MOC]]
- - -

The SMTP protocol is ancient, but too widely used to change easily. It is connection-oriented, like the [[TCP Protocol]].

# Commands

- **MAIL**: Establishes return address, bounce address, sender, and more
- **RCPT**: Establishes address of recipient, repeated per recipient
- **DATA**: Signifies start of message text with header and body

# Email Spoofing

SMTP has no form of authentication, so the sender form can be manipulated.

## SPF

The Sender Policy Framework checks domain name by DNS list. This is useful for small organizations, but not for outsourcing to Google and using `@gmail.com`.

## DKIM

Domain Keys Identified Mail uses asymmetric encryption to encrypt sender and receiver.