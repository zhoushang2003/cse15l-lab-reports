# cse15l-lab-reports
## Part1
The following is my code of StringServer.java
``````java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
	ArrayList<String> string = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
			String result = "Shang's strings are:\n";
			for (int i = 0; i < string.size(); i++) {
				result += string.get(i);
				result += "\n";
			}
			return result;
        } else if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
				string.add(parameters[1]);
				String result = "";
                for (int i = 0; i < string.size(); i++) {
					result += string.get(i);
					result += "\n";
				}
				return result;
            }
        }
        return "404 Not Found!";
    }
}


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

``````
<img width="472" alt="截屏2023-01-30 16 42 02" src="https://user-images.githubusercontent.com/52812466/215629411-96e89f83-ab7d-43f3-9f12-b8b678816115.png">
In this picture, I called handleRequest and the main function. The code for the url.getPath().contains(“/add”) section is called. “Hello“ added Parameters, result. Also, the port changes.

<img width="559" alt="截屏2023-01-30 16 42 56" src="https://user-images.githubusercontent.com/52812466/215629404-0ea0020b-cfd9-4ad6-a809-a6cf60da1533.png">
<http://localhost:8000/add?s=How%20old%20are%20you>
In this picture, I called handleRequest and the main function. The code for the url.getPath().contains(“/add”) section is called. “How old are you“ added Parameters, result. Also, the port changes.

## Part2
I would choose the bug of ListExamples.java

### Failure-inducing input
``````java
    private List<String> input1,input2,answer;
	@Before
	public void setUp(){
		input1 = new ArrayList<String>();
		input2 = new ArrayList<String>();
		answer = new ArrayList<String>();

		input1.add("1");
		input1.add("3");
		input2.add("1");
		input2.add("2");
		answer.add("1");
		answer.add("1");
		answer.add("2");
		answer.add("3");

	}
    	@Test
	public void findBugTester() {
		assertEquals(answer, ListExamples.merge(input2, input1));
	}
``````

### No-Failure input
``````java

	@Test 
	public void noBugTester() {
		assertEquals(answer, ListExamples.merge(input1, input2));
	}
``````

##### Screenshot of the output of Junit

<img width="1342" alt="截屏2023-01-30 17 07 46" src="https://user-images.githubusercontent.com/52812466/215633124-017c2b32-a14c-4668-ba6c-f52c79478006.png">

### Before- and After- code

#### Before code
``````java
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
    return result;
  }
``````
How to fix the issue: In the last while loop, the original code wants to add elements from list2 that are not added to the result. After each element is added, index2 should be added by 1, so we can add the next element. However, the original code wrote index1 plus 1, so we should change it to index2 plus 1.

#### After code
``````java
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }
``````
## Part3
I learned some basic web server syntax. Improved bug-finding ability. What I learned most was writing the Lab Report section. I learned how to use markdown, the color of java code, and change the font of the title.
