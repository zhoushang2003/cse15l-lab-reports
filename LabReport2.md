# cse15l-lab-reports
## Part1
<img width="442" alt="截屏2023-01-30 16 43 08" src="https://user-images.githubusercontent.com/52812466/215629381-7f34f0bd-d6aa-4441-837a-98e5bbc75d7f.png">

<img width="559" alt="截屏2023-01-30 16 42 56" src="https://user-images.githubusercontent.com/52812466/215629404-0ea0020b-cfd9-4ad6-a809-a6cf60da1533.png">

<img width="472" alt="截屏2023-01-30 16 42 02" src="https://user-images.githubusercontent.com/52812466/215629411-96e89f83-ab7d-43f3-9f12-b8b678816115.png">


<http://localhost:8000/add?s=How%20old%20are%20you>


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
How to fix the issue: 
#### After code
``````
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

