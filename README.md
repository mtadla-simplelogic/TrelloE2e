## Trello End2End

## Przygotowanie do zadania 
    1. Stwórz kolekcję o nazwie Trello

    2. Stwórz zmienne środowiskowe:
    - baseURl -> wstaw tutaj adres API trello
    - key -> wstaw swój api-key
    - token -> wstaw swój token
    
    3. Stwórz zmienne w kolekcji i nie przypisuj im żadnej wartości
    - boardId
    - todoId
    - doneId
    - cardId
    - actionId
    
    4. W kolekcji Trello dodaj pre-request skrypt, który do każdego zapytania doda twój api-key oraz token jako query param

## Użyj dokumentacji API, aby wykonać poniższe zapytania:

https://developer.atlassian.com/cloud/trello/rest/

###  1. Create a Board - POST /1/boards/
    Stwórz tablicę, jako nazwę przekaż losowy tekst używając wybranej zmiennej dynamicznej:
    https://learning.postman.com/docs/writing-scripts/script-references/variables-list/
    
    W zakładce test:
    - dodaj test sprawdzający status code
    - zapisz otrzymane ID tablicy jako zmienną kolekcji o nazwie 'boardId'

### 2. Create a new List - POST /1/lists
    Dodaj do tablicy listę o nazwie DONE
    
    W zakładce test:
    - dodaj test sprawdzający status code
    - dodaj test sprawdzający czy nazwa listy otrzymana w response to DONE
    - zapisz otrzymane ID listy jako zmienną kolekcji o nazwie 'doneId'
    
### 3. Create a new List - POST /1/lists
    Dodaj do tablicy listę o nazwie TODO
    
    W zakładce test:
    - dodaj test sprawdzający status code
    - dodaj test sprawdzający czy w body reponse atrybut closed równy jest false
    - zapisz otrzymane ID listy jako zmienną kolekcji o nazwie 'todoId'
    
### 4. Create a new Card - POST /1/cards
    Stwórz nową kartę w liście TODO o nazwie RestIntroduction
    
    W zakładce test:
    - dodaj test sprawdzający status code
    - dodaj test sprawdzający czy w reponse body name karty to RestIntroduction
    - zapisz otrzymane ID   jako zmienną kolekcji o nazwie 'cardId'
    
### 5. Add a new comment to a Card - POST /1/cards/{id}/actions/comments
    Dodaj do karty komentarz o treści “done!”
    
    W zakładce test:
    - dodaj test sprawdzający status code
    - dodaj test sprawdzający czy w reponse body tekst komentarza to "done!"
    - zapisz otrzymane ID tablicy jako zmienną kolekcji o nazwie 'boardId'
    
### 6. Create Reaction for Action - POST /1/actions/{idAction}/reactions
    Utwórz reakcje do komentarza -> wysłanie emoji LIKE 
    
    Wysłanie reakcji zgodnie z dokumentacją bedzie od Ciebie wymagać przekazania 
    w body JSONa określającego, które emojii dodać. Aby dodać LIKE użyj poniży JSON:
        
```json
{
    "unified": "1F44D",
    "shortName": "+1"
}  
```   
    W zakładce test:
    - dodaj test sprawdzający status code
    
### 7. Update a Card - PUT /1/cards/{id}
    Przenieś kartę z TODO na DONE
    
    W zakładce test:
    - dodaj test sprawdzający status code
    
### 8. Delete a Board - DELETE /1/boards/{id} <---- to robimy od razu po create
    Usuń tablicę
    
    W zakładce test:
    - dodaj test sprawdzający status code
    
### 9. Get a Board - GET /1/boards/{id}    
    Spróbuj pobrać dane usuniętej tablicy
    
    W zakładce test:
    - dodaj test sprawdzający status code = 404    
