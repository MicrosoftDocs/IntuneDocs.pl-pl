---
# required metadata

title: Rozwiązywanie problemów z wdrażaniem aplikacji | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune
W tym temacie przedstawiono informacje pomagające w rozwiązywaniu problemów z wdrażaniem aplikacji w usłudze Microsoft Intune.

Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md), aby znaleźć więcej sposobów uzyskania pomocy.


## Typowe problemy z wdrażaniem aplikacji

### Jeśli nie można zalogować się w portalu firmy w usłudze Microsoft Intune

1.  Sprawdź, czy Twoje konto istnieje w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) i czy nie zostało wyłączone.

2.  Upewnij się, że masz udostępnioną obsługę na tym koncie w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854).

3.  W [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) upewnij się, że używasz prawidłowej nazwy użytkownika oraz hasła do logowania się w usłudze Intune i że nazwa użytkownika ma następujący format: **osoba@domena.com**.

### Jeśli w Portalu firmy brakuje informacji kontaktowych działu IT

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Administrator** &gt; **Portal firmy**.

2.  Ustaw szczegóły dla pozycji **Kontakt z działem IT** .

### Jeśli określonych aplikacji nie widać na liście

1.  Upewnij się, że sprawdzasz listę aplikacji dla użytkownika lub urządzenia, na którym aplikacja została wdrożona.

2.  Upewnij się, że urządzenie spełnia wymagania aplikacji.

### Jeśli wystąpi błąd podczas pobierania aplikacji

1.  Upewnij się, że jednocześnie występuje tylko jedno pobieranie na użytkownika. Każdy użytkownik może pobierać tylko jedną aplikację naraz.

2.  Upewnij się, że nie ma zbyt wielu równoczesnych pobrań dla konta. Poczekaj kilka minut, a następnie spróbuj ponownie.

3.  Jeśli zostanie wyświetlony natywny komunikat systemu iOS, że instalacja nie jest możliwa, że została anulowana lub że trzeba ponowić próbę, może to wynikać z dużego natężenia ruchu sieciowego. Poczekaj kilka minut, a następnie spróbuj ponownie.

4.  Jeśli pasek postępu pobierania aplikacji dla systemu iOS pokazuje ukończenie pobierania, ale instalacja aplikacji kończy się niepowodzeniem, przyczyną może być problem z udostępnionymi plikami aplikacji.

### Jeśli link do aplikacji dla systemu iOS umożliwia przejście do poprzedniej lokalizacji w sklepie iTunes

1.  Bieżąca sesja sklepu iTunes App Store otwiera się na poprzedniej stronie aplikacji.

2.  Zamknij sklep iTunes App Store na urządzeniu i ponownie spróbuj użyć linku.

### Jeśli wystąpi błąd podczas uruchamiania aplikacji dla systemu iOS

1.  Data wygaśnięcia aplikacji może być nieprawidłowa.

### Jeśli podczas przekazywania aplikacja zablokuje się w stanie „w toku”

1.  Podczas przekazywania aplikacji najpierw dodawane są metadane, a po nich pakiet aplikacji. Po przekazaniu metadanych aplikacja pojawi się ze stanem „w toku”. Jeśli aplikacja jest „w toku” przez zbyt długi czas, usuń ją, a następnie przekaż ponownie.

2.  Należy pamiętać, aby nie zarządzać wdrażaniem aplikacji w czasie, gdy jest ona w stanie „w toku”.

### Jeśli wystąpi awaria podczas instalowania aplikacji dla systemu iOS

1.  Upewnij się, że zapora organizacji zezwala na dostęp do witryn sieci Web obsługi administracyjnej i certyfikacji firmy Apple.

2.  Więcej informacji zawiera dokumentacja dla deweloperów firmy Apple.

### Błąd: Wydawca nie istnieje
Używasz polecenia **Dodaj inną umowę dotyczącą oprogramowania**, aby dodać umowę licencyjną innej firmy. Próbujesz dodać wydawcę na stronie **Inne umowy licencjonowania oprogramowania**. Ta strona zawiera listę istniejących wydawców w kolejności alfabetycznej.
Wprowadzasz brakującego wydawcę, ale występuje błąd **Wydawca nie istnieje**. 

To jest celowe. Usługa Intune zapewnia śledzenie licencji tylko dla popularnych tytułów oprogramowania. Usługa Intune wymaga co najmniej 4 osobnych kont raportujących oprogramowanie, zanim staje się dostępna jako opcja obciążenia związanego z licencjonowaniem.

### Jeśli zarządzane aplikacje nie zgłaszają stanu instalacji

Przed zaktualizowaniem usługi Microsoft Intune w listopadzie 2014 r. nie zebrano informacji o stanie instalacji zarządzanych aplikacji. W przypadku urządzeń, na których zarządzane aplikacje zostały zainstalowane przed tą aktualizacją usługi, zaktualizuj każde skojarzone wdrożenie aplikacji przy użyciu odpowiedniej akcji wdrażania (na przykład **Dostępna instalacja**). Poszczególne urządzenia zaktualizują aplikacje podczas automatycznego sprawdzania dostępnych aplikacji. Aby uzyskać więcej informacji, zobacz [Aktualizowanie aplikacji przy użyciu usługi Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Kody błędów wdrażania aplikacji
Poniższa tabela zawiera listę typowych błędów, które mogą wystąpić podczas wdrażania aplikacji przy użyciu usługi Intune, ich prawdopodobne przyczyny oraz możliwe rozwiązania pomagające w rozwiązywaniu tych problemów.

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (błąd klienta)|Aby zainstalować tę aplikację, wymagany jest system z obsługą ładowania bezpośredniego.|Upewnij się, że pakiet aplikacji jest podpisany przy użyciu zaufanego podpisu i zainstalowany na urządzeniu przyłączonym do domeny, które ma włączone zasady AllowAllTrustedApps, lub na urządzeniu, które ma licencję ładowania bezpośredniego systemu Windows z włączonymi zasadami AllowAllTrustedApps (stosowane podczas rejestrowania urządzenia z systemem Windows RT).|
|0x80073CF0|Nie można otworzyć pakietu.|Możliwe przyczyny:<br /><br />— pakiet nie został podpisany.<br />— nazwa wydawcy jest niezgodna z podmiotem certyfikatu podpisywania.<br /><br />Sprawdź dziennik zdarzeń AppxPackagingOM, aby uzyskać więcej informacji.|
|0x80073CF3|Niepowodzenie aktualizacji, błąd weryfikacji zależności lub konflikt pakietu|Możliwe przyczyny:<br /><br />— przychodzący pakiet powoduje konflikt z zainstalowanym pakietem.<br />— określona zależność pakietu nie została odnaleziona.<br />— pakiet nie obsługuje poprawnej architektury procesora.<br /><br />Sprawdź dziennik zdarzeń AppXDeployment-Server, aby uzyskać więcej informacji.|
|0x80073CFB|Dany pakiet jest już zainstalowany i jego ponowna instalacja jest zablokowana|Ten błąd może pojawić się w przypadku instalowania pakietu, który nie jest identyczny z pakietem już zainstalowanym. Upewnij się , że podpis cyfrowy jest również częścią pakietu. Jeśli pakiet został ponownie skompilowany lub ponownie podpisany, nie jest już bitowo identyczny z wcześniej zainstalowanym pakietem. Dostępne są następujące dwie opcje naprawienia tego błędu:<br /><br />— zwiększenie numeru wersji aplikacji, a następnie ponowne skompilowanie i ponowne podpisanie pakietu.<br />— usunięcie starego pakietu dla każdego użytkownika w systemie przed zainstalowaniem nowego pakietu.|

### Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=May16_HO4-->


