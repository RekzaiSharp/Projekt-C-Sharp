# Integration Test
In Maven erfolgt der Integration Test über eine vordefinierte Integration-Test-Klasse.
Er wird mittels ``mvn verify`` initialisiert.

<u>Vorbedingungen:</u>
1. Eine Integration-Test-Klasse muss für die zu testende Konfiguration geschrieben werden! (Für die Todo list stand uns eine vordefinierte Klasse bereits zur Verfügung.)
2. Die Integration-Test-Klasse muss in einem anderen Ordner liegen als die zu testenden Dateien.
3. Die Klasse muss in der POM.xml-Konfigurationsdatei definiert sein.
	Dies geschieht normalerweise über einen Verweis zum Dateipfad über das \<include>-Tag (bzw. \<includeFile>) mittels Pattern oder Regex. Wird kein \<include>-Tag angegeben, greift die folgende Default-Konfiguration:
```
<includes>
    <include>**/IT*.java</include>
    <include>**/*IT.java</include>
    <include>**/*ITCase.java</include>
</includes>
```
4. Das [maven-failsafe-plugin](https://maven.apache.org/surefire/maven-failsafe-plugin/usage.html) muss in der POM.xml importiert und für die Integration Test Stage implementiert werden.


<b> Beispiel für die Todo list:</b>
```
  <plugin>
	            <groupId>org.apache.maven.plugins</groupId>

                <artifactId>maven-failsafe-plugin</artifactId>

                <version>3.0.0-M5</version>

                <executions>

                    <execution>

                        <goals>

                            <goal>integration-test</goal>

                        </goals>

                        <configuration>

                            <includes>

                                <include>**IntegrationTest**</include>

                            </includes>

                        </configuration>

                    </execution>

                </executions>

            </plugin>
```

<b>Integration-Test-Klasse für die Todo list:</b>

```
package th.ab.demo.todolist.unittest;

import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.extension.ExtendWith;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.Mockito;
import org.mockito.junit.jupiter.MockitoExtension;
import th.ab.demo.todolist.Todo;
import th.ab.demo.todolist.TodoController;
import th.ab.demo.todolist.TodoRepository;

import static org.hamcrest.MatcherAssert.assertThat;
import static org.mockito.Mockito.*;

@ExtendWith(MockitoExtension.class)
class TodolistUnitTests {

	@Mock
	TodoRepository todoRepository;

	@InjectMocks
	TodoController todoController = new TodoController();

	@Test
	void deleteTodo() {
		when(todoRepository.existsById(any())).thenReturn(true);

		todoController.delete(5L);

		verify(todoRepository).deleteById(5L);
	}

	@Test
	void addTodo() {
		Todo todo = new Todo(4L, "Test");
		todoController.add(todo);

		verify(todoRepository).save(todo);
	}


}
```


## Quellen:
https://www.testwithspring.com/lesson/running-integration-tests-with-maven
https://maven.apache.org/surefire/maven-failsafe-plugin/integration-test-mojo.html