# PROJEKT MOJE FILMY
Projekt ten składa się z następujących komponentów:
* **BACKEND/API**: Stworzone przy użyciu .NET
* **FRONTEND/UI**: Stworzone przy użyciue Vue JS
* **STYLE**: Zaimplementowane przy pomocy BOOTSTRAP 5
* **Baza Danych**: API wysyła REQUESTY do bazy danych utworzonej za pomocą *Neon Cloud PostgreSQL*. Baza danych w projekcie jest jawna ze względu na ułatwienie dostępu i ułatwienie konfiguracji projektu - jest to rozwiązanie niebezpieczne, ale prostsze w implementecji.

- Pozwala dodać nowy film (np. „Incepcja”, „Shrek”)
- wyświetla wszystkie filmy bazy

# Wymagania
- .NET SDK 6.0 (lub nowszy) dla API
- VS 2022 z odpowiednimi rozszerzeniami

# PORTY z których domyślnie korzysta projekt:
- API korzysta z portu 5246, na pętli zwrotnej (lub portu 5000)
- UI korzysta z portu 3500, na pętli zwrotnej

# Instrukcja Uruchomienia (terminal vs code)
- Klonowanie Repozytorium do folderu: np. **git clone https://github.com/TrueHardLive/moje-filmy-projekt.git**
- Następnie trzeba przejść do folderu w którym jest zawartość repozytorium **cd moje-filmy-projekt**
- Odpalenie API: ** cd .\api\Project\ **
- * dotnet restore
  * dotnet run
- Następnie otworzyć nowy terminal (np. vs code) i wpisać **cd .\moje-filmy-projekt\ui\biblioteka-ui\  **
- * npm install
  * npm run dev

# OPIS PLIKÓW DLA api/Project/
| Plik/folder                       | Co robi?                                                                         |
| --------------------------------- | -------------------------------------------------------------------------------- |
| `Controllers/MoviesController.cs` | Główna logika API – tu trafiają zapytania z przeglądarki: GET, POST, PUT, DELETE |
| `Models/Movie.cs`                 | Klasa opisująca film (np. tytuł, reżyser, rok, opis)                             |
| `Data/DataContext.cs`             | Połączenie z bazą danych – tu .NET wie gdzie wysyłać zapytania                   |
| `Program.cs`                      | Start aplikacji, rejestracja API, konfiguracja                                   |
| `appsettings.json`                | Ustawienia, np. dane logowania do bazy PostgreSQL                                |

# OPIS PLIKÓW DLA ui/biblioteka-ui/
| Plik/folder                    | Co robi?                                                                                 |
| ------------------------------ | ---------------------------------------------------------------------------------------- |
| `src/views/HomeView.vue`       | Główna strona – pokazuje listę filmów                                                    |
| `src/components/MovieForm.vue` | Formularz do dodawania/edycji filmu                                                      |
| `src/components/MovieItem.vue` | Jedna linijka w tabeli – pojedynczy film                                                 |
| `src/services/MovieService.js` | Tu są funkcje `getAll()`, `addMovie()`, `updateMovie()` itd. – wysyłają zapytania do API |
| `vite.config.js`               | Konfiguracja projektu frontendowego                                                      |
| `package.json`                 | Lista paczek npm (Vue, Bootstrap itd.) i skrypty (`npm run dev`, `build` itd.)           |