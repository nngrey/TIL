# MIME type

At a recent interview, I was asked a question about uploading files and security and the answer was MIME types. So what is a MIME type?

>A MIME type is a label for a given type of data so software can know how to handle the data. It serves the same purpose on the Internet that file extensions do on Microsoft Windows. A MIME type has two parts: a type and a subtype. They are separated by a slash (/). If a server says "This is text/html" the client can go "Ah, this is an HTML document, I can render that internally", while if the server says "This is application/pdf" the client can go "Ah, I need to launch the FoxIt PDF Reader plugin." [More](https://stackoverflow.com/questions/3828352/what-is-a-mime-type)

I'm still not sure about using MIME types for security. One example, though, is to use an application that detects the MIME type (sometimes called a MIME sniffer). That way if someone uploads a php file named `i_am_lying.jpg`. The MIME type can be detected despite the erroneous file extension. [More](https://github.com/deviantech/carrierwave-mimetype-fu)
