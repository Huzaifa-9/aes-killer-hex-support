# aes-killer-hex-support
aes-killer hex support added


    public byte[] hexStringToByteArray(String hexString) {
        int length = hexString.length();
        byte[] byteArray = new byte[length / 2];
        for (int i = 0; i < length; i += 2) {
            byteArray[i / 2] = (byte) ((Character.digit(hexString.charAt(i), 16) << 4)
                                       + Character.digit(hexString.charAt(i+1), 16));
        }
        return byteArray;
    }
    
    public String byteArrayToHexString(byte[] byteArray) {
        StringBuilder hexString = new StringBuilder();
        for (byte b : byteArray) {
            String hex = Integer.toHexString(0xFF & b);
            if (hex.length() == 1) {
                hexString.append('0'); // pad with leading zero if necessary
            }
            hexString.append(hex);
        }
        return hexString.toString();
    }
    
![image](https://github.com/user-attachments/assets/d983a3d6-d35c-4623-bc8c-deb2063856ff)
