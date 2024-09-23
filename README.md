# FluentResults in .NET 8.0
+ https://github.com/gtechsltn/FluentAssertions_NET8
+ https://github.com/gtechsltn/FluentResults_NET8
+ **FluentResults**
+ FluentResults.Extensions.FluentAssertions
+ FluentResults.Extensions.AspNetCore
+ **FluentAssertions**

# Throw Exception Best Practices in .NET (C#)
https://mabhishekit.medium.com/net-c-throw-exception-best-practices-3b8931fb4010

## FluentResults: A generalised Result object implementation for .NET/C#
https://github.com/altmann/FluentResults

## FluentResults.Extensions.FluentAssertions
+ https://www.nuget.org/packages/FluentResults
+ https://www.nuget.org/packages/FluentResults.Extensions.FluentAssertions/

## FluentResults.Extensions.AspNetCore
+ https://www.nuget.org/packages/FluentResults
+ https://www.nuget.org/packages/FluentResults.Extensions.AspNetCore/

## Fluent Assertions

Extension methods to fluently assert the outcome of .NET tests

https://fluentassertions.com/

https://github.com/fluentassertions/fluentassertions

### Writing Elegant Tests in .NET with Fluent Assertions

https://medium.com/@kova98/writing-elegant-tests-in-net-with-fluentassertions-5cb8f56a31ab

### xUnit and Fluent Assertions

https://www.infoworld.com/article/2338880/how-to-use-fluent-assertions-in-c-sharp.html

### The complete Fluent Assertions example code

The complete source code of our unit test project is given below for your reference.

```
using FluentAssertions;
namespace FluentAssertionsDemo
{
    public class Author
    {
        public int Id { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; } = string.Empty;
        public string Address { get; set; } = string.Empty;
    }
    public class FluentAssertionsUnitTests
    {

        [Fact]
        public void Verify_Subject_Identification()
        {
            string username = "joydipkanjilal@yahoo.com";
            username.Should().Be("joydipkanjilal@yahoo.com");
        }

        [Fact]
        public void Verify_The_Value_Of_An_Integer_Variable()
        {
            int i = 100;
            i.Should().Be(100);
            i.Should().BePositive();
            i.Should().BeGreaterThanOrEqualTo(100);
            i.Should().BeGreaterThan(50);
            i.Should().BeLessThanOrEqualTo(1000);
            i.Should().BeLessThan(500);
            i.Should().BeInRange(1, 100);
        }

        [Fact]
        public void Verify_The_Value_And_Type_Of_A_Reference_Type()
        {
            Author author1 = new Author();
            Author author = new Author();
            author.Id = 1;
            author.FirstName = "Joydip";
            author.LastName = "Kanjilal";
            author.Address = "Hyderabad, INDIA";
            author.Should().NotBeNull();
            author.Should().BeOfType<Author>();
        }

        [Fact]
        public void Verify_The_Value_Of_A_String_Object()
        {
            string str = "Hello World";
            str.Should().NotBeNullOrEmpty();
            str.Should().NotBeNullOrWhiteSpace();
        }

        [Fact]
        public void Verify_The_Value_Of_A_Boolean_Variable()
        {
            bool isTrue = true;
            isTrue.Should().BeTrue();
            isTrue = false;
            isTrue.Should().NotBe(false);
        }

        [Fact]
        public void Verify_That_A_String_Begins_Ends_And_Contains_A_Particular_Phase()
        {
            string actual = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
            var result = actual.Should().StartWith("ABCDE").And.EndWith("XYZ").
                And.Contain("JK").And.HaveLength(26);
        }

        [Fact]
        public void Verify_The_ISBN_Author_Name_And_Title_Of_A_Book_Without_Fluent_Assertions()
        {
            string isbn = "978-9388511605";
            string author = "Joydip Kanjilal";
            string title = "Mastering C# 8.0";
            Assert.Equal("9780321146533", isbn);
            Assert.Equal("Joydip Kanjilal", author);
            Assert.Equal("Mastering C# 8.0", title);
        }

        [Fact]
        public void Verify_The_ISBN_Author_Name_And_Title_Of_A_Book_With_Fluent_Assertions()
        {
            string isbn = "978-9388511605";
            string author = "Joydip Kanjilal";
            string title = "Mastering C# 8.0";
            Assert.Equal("978-9388511605", isbn);
            Assert.Equal("Joydip Kanjilal", author);
            Assert.Equal("Mastering C# 8.0", title);
        }
    }
}
```
