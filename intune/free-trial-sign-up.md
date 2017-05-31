---
title: "Tworzenie konta w celu korzystania z 30-dniowej bezpłatnej wersji próbnej"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: sposób tworzenia konta w celu korzystania z usługi Intune na platformie Azure."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3be43e12abc1cf90da3584450ddd56ab63bdfac1
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Tworzenie konta w celu korzystania z bezpłatnej wersji próbnej usługi Microsoft Intune w wersji zapoznawczej portalu Azure Portal

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

W tym artykule przedstawiono kolejne kroki procesu tworzenia konta w celu korzystania z wersji próbnej autonomicznej usługi Intune w wersji zapoznawczej portalu Azure Portal. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Odwiedź stronę [Rejestracja w usłudze Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) i wypełnij formularz rejestracji, aby zamówić subskrypcję wersji próbnej.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Obraz przedstawiający stronę rejestracji](./media/1-clicking-try.png)

 > [!TIP]
> Jeśli większość operacji IT i użytkowników korzysta z innych ustawień regionalnych, możesz wybrać odpowiednie ustawienia regionalne w obszarze **Where's your company located?** (Gdzie znajduje się Twoja firma?).

2. Pod koniec procesu rejestracji zostanie wyświetlony komunikat z informacjami o nowym koncie. <br/> ![Obraz przedstawiający informacje o koncie](./media/2-end-of-sign-up-process.png) <br/>Jeśli na tym etapie klikniesz pozycję **You're ready to go** (Możemy zaczynać), nastąpi przekierowanie do centrum administracyjnego usługi Office 365, gdzie można dodać użytkowników do środowiska testowego. <br/><br/>Jeśli jednak chcesz przejść bezpośrednio do wersji zapoznawczej portalu usługi Intune Azure, otwórz nowe okno przeglądarki i wprowadź adres **https://portal.azure.com** w pasku adresu. Nastąpi przekierowanie do strony logowania platformy Azure, gdzie możesz się zalogować przy użyciu otrzymanych poświadczeń. Używaj tego adresu za każdym razem, gdy chcesz zalogować się do wersji próbnej usługi Intune. <br/> ![Obraz przedstawiający stronę logowania portalu Azure Portal](./media/azure-portal-signin.png)

Po pierwszym zalogowaniu się do wersji zapoznawczej usługi Intune na platformie Azure usługa Intune może nie być widoczna na pulpicie nawigacyjnym platformy Azure. Aby dodać usługę Intune do pulpitu nawigacyjnego platformy Azure:
1. Wybierz pozycję **Więcej usług >** na liście usług platformy Azure z lewej strony pulpitu nawigacyjnego, a następnie wprowadź wyrażenie **Intune** w polu wyszukiwania.
2. Wybierz z listy pozycję **Intune**, a następnie wybierz gwiazdkę, aby dodać usługę do listy usług.<br/> ![Obraz przedstawiający wybieranie usługi Intune z listy usług](./media/azure-add-intune1.png)
3. Następnie z listy usług wybierz pozycję **Intune**, aby otworzyć pulpit nawigacyjny usługi Intune.

Po utworzeniu konta w celu korzystania z wersji próbnej na adres e-mail podany w procesie rejestracji zostanie wysłana wiadomość e-mail zawierająca informacje o koncie. Stanowi ona potwierdzenie, że Twoja wersja próbna jest aktywna.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Zachowywanie prostego środowiska pracy administratora
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Na potrzeby wersji zapoznawczej usługi Intune Azure będą używane trzy portale:
- Pulpit nawigacyjny usługi Intune na platformie Azure ([portal.azure.com](https://portal.azure.com)), który umożliwia zapoznanie się z [możliwościami usługi Intune w portalu Azure Portal](what-is-intune.md).
- Centrum administracyjne usługi Office 365 ([portal.office.com](https://portal.office.com)), gdzie możesz dodawać użytkowników i zarządzać nimi, jeśli nie używasz w tym celu usługi Azure Active Directory. Możesz również zarządzać innymi aspektami konta, w tym rozliczeniami i pomocą techniczną.
- Klasyczna konsola administracyjna usługi Intune ([manage.microsoft.com](https://manage.microsoft.com)), która pozwala zapoznać się z funkcjami, które nie zostały jeszcze dodane do platformy Azure.

Zazwyczaj praca odbywa się na pulpicie nawigacyjnym usługi Intune, co pokazano poniżej. Jest to witryna, w której można konfigurować grupy, zasady, urządzenia i aplikacje oraz zarządzać nimi.

Możesz przejść do konsoli administracyjnej klasycznego portalu usługi Intune z pulpitu nawigacyjnego, wybierając kafelek **Otwórz klasyczny portal usługi Intune**.

Aby powrócić do wersji zapoznawczej usługi Intune Azure, wprowadź adres https://portal.azure.com na pasku adresu przeglądarki, a następnie ponownie wybierz pozycję **Intune** z listy usług.

 ![Obraz przedstawiający pulpit nawigacyjny usługi Intune](./media/intune-azure-dashboard.png)


Jednak do dodawania użytkowników i zarządzania nimi oraz wykonywania innych czynności związanych z obsługą konta, w tym z rozliczeniami i pomocą techniczną, będziesz używać przedstawionego poniżej Centrum administracyjnego usługi Office 365.

![Ilustracja przedstawiająca Centrum administracyjne usługi Office 365](./media/office-admin-center.png)

Aby przejść z Centrum administracyjnego usługi Office 365 na pulpit nawigacyjny usługi Intune, wprowadź adres https://portal.azure.com na pasku adresu przeglądarki. Wybierz pozycję **Intune** na liście usług.

Aby wrócić z usługi Intune do Centrum administracyjnego usługi Office 365, wprowadź adres https://portal.office.com na pasku adresu przeglądarki. Jeśli użytkownik jest już zalogowany w usłudze Intune, nastąpi przekierowanie bezpośrednio do Centrum administracyjnego usługi Office 365.

## <a name="next-steps"></a>Następne kroki

### <a name="intune-azure-preview"></a>Wersja zapoznawcza usługi Intune Azure
Dowiedz się więcej na temat [usługi Intune w wersji zapoznawczej witryny Azure Portal](what-is-intune.md)
### <a name="classic-intune"></a>Klasyczny portal usługi Intune
Scenariusz oceny: [Ocena zarządzania urządzeniami przenośnymi za pomocą usługi Microsoft Intune](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integracja z innymi produktami
Dowiedz się więcej o korzystaniu z kont użytkowników usługi Azure Active Directory za pomocą usługi Intune:
- [Wymagania dotyczące tożsamości](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Wymagania dotyczące synchronizacji katalogu](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Wymagania uwierzytelniania wieloskładnikowego](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Dowiedz się więcej na temat używania [usługi Intune z programem System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)

