Challenge
=========

Find sum of numbers present in a given file.

//Read the given File and find the sum of integer present in the file.
//JAVA Code

public class FileReaderIntValues {

	public static int readInt(String filename) {
		StringBuilder data = new StringBuilder();
		String line;
		int sum = 0;

		File file = new File(filename);

		try {
			FileReader filereader = new FileReader(file);
			BufferedReader bufferedreader = new BufferedReader(filereader);
			while ((line = bufferedreader.readLine()) != null) {
				data.append(line);
				// System.out.println(Integer.parseInt(line));
			}

			String sentence = data.toString();
			String[] words = sentence.split(" ");

			for (int i = 0; i < words.length; i++) {
				int integer = new Integer((int) words[i].charAt(0));
				if (integer >= 48 && integer <= 57) {
					sum = sum + Integer.parseInt(words[i]);
					System.out.println(words[i] + " ");
				}
			}
			bufferedreader.close();
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}
		return sum;
	}

	public static void main(String[] ch) {
		System.out.println("Sum of Integer in a given file is : "+readInt("text.txt"));
	}
}

