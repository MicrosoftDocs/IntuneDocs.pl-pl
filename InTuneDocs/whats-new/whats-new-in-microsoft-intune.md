---
title: Co nowego | Microsoft Docs
description: "Sprawdź, co nowego w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Co nowego w usłudze Microsoft Intune — marzec 2017
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="support-for-skycure"></a>Obsługa aplikacji Skycure

Dostęp urządzeń przenośnych do zasobów firmy można obecnie kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez aplikację Skycure. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną usługą Skycure. Są to na przykład:

- Ochrona fizyczna
- Ochrona sieciowa
- Ochrona aplikacji
- Ochrona przed lukami w zabezpieczeniach

Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez aplikację Skycure włączaną przy użyciu zasad zgodności urządzeń usługi Intune. Przy użyciu tych zasad można zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia. Aby uzyskać więcej informacji, zobacz [Łącznik Skycure Mobile Threat Defense](/intune/deploy-use/skycure-mobile-threat-defense-connector).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->

Interfejs użytkownika aplikacji Portal firmy dla systemu Android zostanie zaktualizowany w celu zapewnienia bardziej nowoczesnego wyglądu i działania oraz udoskonalenia środowiska pracy. Znaczące zmiany:

- Kolory: nagłówki kart w aplikacji Portal firmy mają kolor wybrany przez zespół IT.
- Aplikacje: na karcie **Aplikacje** zaktualizowano przyciski **Polecane aplikacje** i **Wszystkie aplikacje**.
- Wyszukiwanie: przycisk **Wyszukaj** na karcie **Aplikacje** jest teraz przestawnym przyciskiem akcji.
- Poruszanie się w obrębie aplikacji: w widoku **Wszystkie aplikacje** jest dostępny widok z kartami **Polecane**, **Wszystkie** i **Kategorie**, które ułatwiają nawigację.
- Pomoc techniczna: zaktualizowano karty **Moje urządzenia** i **Kontakt z działem IT** w celu poprawy czytelności.

Aby uzyskać więcej informacji o tych zmianach, zobacz artykuł [Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->

W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Podpisywanie skryptu dla aplikacji Portal firmy systemu Windows 10<!--941642-->

Jeśli musisz pobrać i ładować bezpośrednio aplikację Portal firmy dla systemu Windows 10, możesz teraz korzystać ze skryptu upraszczającego i usprawniającego proces podpisywania aplikacji w organizacji.   Aby pobrać skrypt i instrukcje dotyczące korzystania z niego, zobacz temat [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Microsoft Intune – skrypt podpisywania) dla aplikacji Portal firmy systemu Windows 10 w galerii TechNet. Więcej szczegółów dotyczących tego powiadomienia można znaleźć w artykule [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Aktualizowanie aplikacji Portal firmy dla systemu Windows 10) na blogu zespołu pomocy technicznej usługi Intune.


## <a name="notices"></a>Uwagi

### <a name="support-for-ios-103"></a>Obsługa systemu iOS 10.3

Wersja systemu iOS 10.3 została udostępniona użytkownikom 27 marca 2017 r. Wszystkie istniejące scenariusze dotyczące zarządzania urządzeniami przenośnymi i aplikacjami mobilnymi w usłudze Intune mają zastosowanie do najnowszej wersji systemu operacyjnego firmy Apple. Przewidujemy, że wszystkie obecnie dostępne funkcje usługi Intune do zarządzania urządzeniami z systemem iOS będą nadal działać po uaktualnieniu urządzeń i aplikacji do systemu iOS 10.3 przez użytkowników.

Obecnie nie występują żadne znane problemy. W przypadku wystąpienia jakichkolwiek problemów związanych z systemem operacyjnym iOS w wersji 10.3 zachęcamy do kontaktu z [zespołem pomocy technicznej usługi Intune](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Ulepszona obsługa systemu Android dla użytkowników w Chinach <!--720444-->

Ponieważ Sklep Google Play jest niedostępny w Chinach, aplikacje na urządzenia z systemem Android należy uzyskiwać z chińskich platform oferujących aplikacje. Aplikacja Portal firmy będzie obsługiwać ten przepływ pracy, przekierowując użytkowników systemu Android w Chinach na strony umożliwiające pobranie aplikacji Portal firmy i Outlook z lokalnych sklepów z aplikacjami. Pozwoli to udoskonalić środowisko pracy w przypadku włączenia zasad dostępu warunkowego — zarówno dla zarządzania urządzeniami przenośnymi, jak i zarządzania aplikacjami mobilnymi. Aplikacje Portal firmy i Outlook dla systemu Android są dostępne w następujących chińskich sklepach z aplikacjami:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Najlepsze rozwiązanie: upewnij się, że aplikacje portalu firmy są aktualne<!--879465-->

W grudniu 2016 roku opublikowaliśmy aktualizację włączającą wymuszanie uwierzytelniania wieloskładnikowego (MFA, multi-factor authentication) dla grupy użytkowników rejestrujących urządzenie z systemem iOS, Android, Windows 8.1 i nowszym lub Windows Phone 8.1 i nowszym. Ta funkcja nie może działać bez niektórych podstawowych wersji aplikacji Portal firmy dla systemów Android (w wersji 5.0.3419.0 lub nowszej) i iOS (w wersji 2.1.17 lub nowszej).

Firma Microsoft nieustannie ulepsza usługę Intune poprzez dodawanie nowych funkcji do konsoli i aplikacji Portal firmy na wszystkich obsługiwanych platformach. W rezultacie firma Microsoft wydaje tylko poprawki dotyczące problemów znalezionych w bieżącej wersji aplikacji Portal firmy. Dlatego zaleca się używanie najnowszych wersji aplikacji Portal firmy w celu uzyskania możliwie najwygodniejszego sposobu pracy użytkownika.

>[!Tip]
> Użytkownicy powinni skonfigurować swoje urządzenia do automatycznego aktualizowania aplikacji z właściwego sklepu z aplikacjami. Jeśli aplikacja Portal firmy systemu Android została udostępniona w udziale sieciowym, jej najnowszą wersję możesz pobrać z [Centrum pobierania firmy Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Obszar roboczy Microsoft Teams jest teraz włączony dla usługi MAM w systemach iOS i Android

Firma Microsoft poinformowała o ogólnej dostępności obszaru roboczego Microsoft Teams. Zaktualizowane aplikacje Microsoft Teams dla systemów iOS i Android są teraz włączone wraz z funkcjami zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune, możesz więc zaoferować swoim zespołom możliwość swobodnej pracy na różnych urządzeniach przy jednoczesnym stałym zapewnieniu ochrony konwersacji i danych firmowych. Aby uzyskać więcej informacji, zobacz [Anons Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) na blogu rozwiązania Enterprise Mobility and Security.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](/intune-azure/introduction/whats-new).

> [!Note]
> W przypadku wersji zapoznawczej portalu Azure firma Microsoft jest w trakcie wdrażania aktualizacji przewidzianych w tym miesiącu. Jednak zmiany mogą nie być dostępne od razu ze względu na sposób wdrażania usługi Intune.  Zanim nowe funkcje staną się dostępne, niektóre składniki usługi muszą zostać zaktualizowane sekwencyjnie. Szukaj zmian w wersji zapoznawczej portalu Azure w miarę ich wdrażania w tym miesiącu. Aby uzyskać pełną listę zmian, zobacz artykuł [Co nowego w wersji zapoznawczej usługi Microsoft Intune](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal

Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Wkrótce

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archiwum nowości](whats-new-archive.md)

