# Lab report 1
## This is my lab report
This report includes text and also figures that I linked from my repository.
Like this:
![](https://github.com/cjarro-uky/BAE305-SP24-Lab1/blob/main/20240110_100436.jpg)

Also I can include math functions like this:

$$V(V) = I(A)*R(&Omega;)$$

$$P(W) = I(A)^2*R(&Omega;)$$

Also I have to include code like this:

```c++
void recvWithEndMarker() {
    static byte ndx = 0;
    char endMarker = '\n';
    char rc;
    
    while (mySerial.available() > 0 && newData == false) {
        rc = mySerial.read();

        if (rc != endMarker) {
            receivedChars[ndx] = rc;
            ndx++;
            if (ndx >= numChars) {
                ndx = numChars - 1;
            }
        }
        else {
            receivedChars[ndx] = '\0'; // terminate the string
            ndx = 0;
            newData = true;
        }
    }
}
```