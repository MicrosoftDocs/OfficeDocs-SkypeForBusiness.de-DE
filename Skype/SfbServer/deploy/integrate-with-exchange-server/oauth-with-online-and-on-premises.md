---
title: Integration zwischen Skype für Business Online und Exchange server
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Konfigurieren von OAuth aktiviert-Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Exchange-Integration in featureunterstützung beschriebenen Features.
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216662"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Konfigurieren der Integration zwischen Skype für Unternehmen Online oder Microsoft-Teams und Exchange Server 

Konfigurieren der Integration zwischen Exchange Server und Skype für Business Online ermöglicht die Skype für Geschäfts- und Integration von Exchange-Features beschrieben in [Feature zu unterstützen](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Dieses Thema bezieht sich auf Integration mit Exchange Server 2013 über 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie anfangen

- Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten

-  Sie müssen Berechtigungen zugewiesen werden, bevor Sie dieses Verfahren oder Verfahren ausführen können. Welche Berechtigungen Sie müssen finden Sie im Thema [Exchange and Shell Infrastructure Permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Konfigurieren der Integration zwischen Exchange Server und Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Schritt 1: Konfigurieren von OAuth-Authentifizierung zwischen Exchange Server und Office 365

Führen Sie die Schritte im folgenden Artikel:

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Schritt 2: Erstellen Sie ein neues E-Mail-Konto für die Skype für Business Online oder Teams Partneranwendung

Dieser Schritt ist auf dem Exchange Server ausgeführt. Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen. Dieses Konto wird anschließend im nächsten Schritt gebraucht.

Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation. Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden. Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren. Darüber hinaus die \<DomainControllerFQDN\> sollte der FQDN eines Domänencontrollers sein.

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Schritt 3: Erstellen Sie und aktivieren Sie eine Partneranwendung für Skype für Business Online oder Teams

Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben. Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Überprüfen Ihres Erfolgs

Stellen Sie sicher, dass die Konfiguration korrekt ist, indem Sie überprüfen, dass einige der Features erfolgreich arbeiten. 

1. Vergewissern Sie sich, dass Outlook-Kalender-Delegierung zwischen zwei Benutzern mit Teams mit Exchange Server 2016 oder 2019 Postfächer funktioniert.

2. Vergewissern Sie sich, dass im Gesprächsverlauf von Outlook-Ordner Unterhaltungsverlauf für mobile Clients angezeigt wird.

Betrachten Sie alternativ den Datenverkehr. Des Datenverkehrs in einem OAuth-Handshake ist wirklich charakteristischen (und nicht sehen, wie die Standardauthentifizierung), insbesondere zur Umgehung von Bereichen, wobei Sie Aussteller-Datenverkehr angezeigt, die folgendermaßen aussieht beginnen: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit einem / vor das @-Zeichen), in der Token, die übergeben werden. Benutzernamen und Kennwort an, das die Punkt OAuth wird nicht angezeigt. Aber sehen Sie den Aussteller 'Office' – in diesem Fall ist "4" Skype für Unternehmen – und dem Bereich Ihres Abonnements.

Wenn Sie sicherstellen möchten, dass Sie erfolgreich OAuth verwenden, stellen Sie sicher, dass Sie wissen, was zu erwarten und wissen, wie der Datenverkehr aussehen sollte. [Hier ist zu erwarten, dass](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)dies der Fall ist, hier ist ein ziemlich standard [Beispiel OAuth-Verkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (sehr nützlich zu lesen, obwohl es nicht Aktualisierungstoken verwendet), und es sind Fiddler-Erweiterungen, die Sie in Ihre OAuth JWT (JSON suchen können Web Token).

Es folgt ein [Beispiel für eine einrichten](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), jedoch können Sie diesen Prozess verpflichten sich gerne Netzwerk Tracing-Tools.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
