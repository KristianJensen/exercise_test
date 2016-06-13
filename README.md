# exercise_test
A coding exercise framework for Python

This package enables simple creation of Jupyter notebook-based interactive coding exercises.<br>
Exercise passing criteria are specified via the unittest interface and notebooks with markdown formatted instruction text
can be quickly autogenerated based on an exercise "blueprint" file.

Example of a blueprint for an exercise:

    class Exercise1(exercise_test.Exercise):
        """
        Define a function that sorts an input list.
        """
        name = "Exercise 1"
    
        cell_code = """
            def sort_function(li):
                pass # define your function here
        """
    
        def runTest(self):
            self.assertFalse("sorted(" in self.cell, msg="Try to do it without using 'sorted()'")
            li = [2, 6, 9, 3, 10]
            self.assertEqual(self.main.sort_function(li), sorted(li), "The list is not sorted.")
