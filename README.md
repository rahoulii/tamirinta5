# tamirinta5


public class tamirinta5 {

    public static int myword(String s) {
        int counter = 0;
        for (int i = 0; i <= s.length() - 1; i++) {
            if (Character.isLetter(s.charAt(i))) {
                counter++;
                for (; i <= s.length() - 1; i++) {
                    if (s.charAt(i) == ' ') {
                        i++;
                        break;
                    }
                }
            }
        }
        return counter;
    }

    public static int myword1(String word) {

        if (word == null || word.trim().length() == 0) {
            return 0;
        }

        int counter = 1;

        for (char c : word.trim().toCharArray()) {
            if (c == ' ') {
                counter++;
            }
        }
        return counter;
    }

    public static int myword2(String word) {
        if (word != null || word.length() > 0) {
            return word.trim().length()
                    - word.trim().replaceAll("[ ]", "").length() + 1;
        } else {
            return 0;
        }
    }

    public static int myword3(String word) {
        if (word == null || word.length() == 0) {
            return 0;
        }
        if (word.charAt(0) == ' ') {
            return 1 + myword3(word.substring(1));
        }
        return myword3(word.substring(1));
    }

    public static int myword4(String word) {
        if (word == null || word.length() == 0) {
            return 0;
        }

        String check = word.trim();
        int counter = 1;
        for (int i = 0; i < check.length(); i++) {
            if (i > 0 && Character.isSpaceChar(check.charAt(i))
                    && !Character.isSpaceChar(check.charAt(i - 1))) {
                counter++;
            }
        }
        return counter;
    }
    

}
