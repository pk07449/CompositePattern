# CompositePattern

###Composite pattern is used where we need to treat a group of objects in similar way as a single object. Composite pattern composes objects in term of a tree structure to represent part as well as whole hierarchy. This type of design pattern comes under structural pattern as this pattern creates a tree structure of group of objects.

###This pattern creates a class that contains group of its own objects. This class provides ways to modify its group of same objects.

##Verify the output.

>Employee :[ Name : John, dept : CEO, salary :30000 ]

>Employee :[ Name : Robert, dept : Head Sales, salary :20000 ]

>Employee :[ Name : Richard, dept : Sales, salary :10000 ]

>Employee :[ Name : Rob, dept : Sales, salary :10000 ]

>Employee :[ Name : Micheal, dept : Head Marketing, salary :20000 ]

>Employee :[ Name : Laura, dept : Marketing, salary :10000 ]

>Employee :[ Name : Bob, dept : Marketing, salary :10000 ]


		public static void main(String[] args) {
	
			Employee CEO = new Employee("John", "CEO", 30000);
	
			Employee headSales = new Employee("Robert", "Head Sales", 20000);
	
			Employee headMarketing = new Employee("Micheal", "Head Marketing", 20000);
	
			Employee clerk1 = new Employee("Laura", "Marketing", 10000);
			Employee clerk2 = new Employee("Bob", "Marketing", 10000);
	
			Employee saleExecutive1 = new Employee("Richard", "Sales", 10000);
			Employee saleExecutive2 = new Employee("Rob", "Sales", 10000);
	
			CEO.add(headSales);
			CEO.add(headMarketing);
	
			headSales.add(saleExecutive1);
			headSales.add(saleExecutive2);
	
			headMarketing.add(clerk1);
			headMarketing.add(clerk2);
	
			System.out.println(CEO);
	
			for (Employee headEmployee : CEO.getSubordinate()) {
				System.out.println(headEmployee);
	
				for (Employee employee : headEmployee.getSubordinate()) {
					System.out.println(employee);
				}
			}
		}