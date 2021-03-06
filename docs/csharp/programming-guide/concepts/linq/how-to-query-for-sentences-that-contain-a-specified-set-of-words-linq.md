---
title: 지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: efb0eb60a9695c19e16b507d29ef6994e904cff9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347689"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a>지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)
이 예제에서는 지정된 각 단어 집합과 일치하는 항목이 포함된 문장을 텍스트 파일에서 찾는 방법을 보여 줍니다. 이 예제에서는 검색어 배열이 하드 코드되어 있지만 런타임에 동적으로 채워질 수도 있습니다. 이 예제에서 쿼리는 "Historically", "data" 및 "integrated" 단어가 포함된 문장을 반환합니다.  
  
## <a name="example"></a>예제  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.   
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 쿼리에서는 먼저 텍스트를 문장으로 분할한 다음 문장을 각 단어가 포함된 문자열 배열로 분할합니다. 각 배열에 대해 <xref:System.Linq.Enumerable.Distinct%2A> 메서드가 모든 중복 단어를 제거한 다음 쿼리가 단어 배열 및 `wordsToMatch` 배열에 대해 <xref:System.Linq.Enumerable.Intersect%2A> 작업을 수행합니다. 교집합의 개수가 `wordsToMatch` 배열의 개수와 같으면 단어에서 모든 단어가 발견된 것이며 원래 문장이 반환됩니다.  
  
 <xref:System.String.Split%2A> 호출에서는 문자열의 구분 기호를 제거하기 위해 문장 부호가 구분 기호로 사용되었습니다. 이렇게 하지 않았다면, 예를 들어 `wordsToMatch` 배열의 "Historically"와 일치하지 않는 "Historically," 문자열이 있을 수 있습니다. 소스 텍스트에서 찾은 문장 부호 유형에 따라 추가 구분 기호를 사용해야 할 수도 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.

## <a name="see-also"></a>참조

- [LINQ 및 문자열(C#)](./linq-and-strings.md)
