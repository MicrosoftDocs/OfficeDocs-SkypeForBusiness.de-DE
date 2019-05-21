---
title: Integration von Skype for Business Online und Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Wenn Sie die OAuth-Authentifizierung zwischen Exchange lokal und Skype for Business Online konfigurieren, werden die unter Funktionsunterstützung beschriebenen Funktionen für Skype for Business und die Exchange-Integration aktiviert.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278126"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Konfigurieren der Integration zwischen Skype for Business Online oder Microsoft Teams und Exchange Server 

Durch die Konfiguration der Integration zwischen Exchange Server und Skype for Business Online werden die unter [Funktionsunterstützung](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)beschriebenen Funktionen für Skype for Business und Exchange integriert.

Dieses Thema bezieht sich auf die Integration in Exchange Server 2013 bis 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie anfangen

- Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten

-  Sie müssen Berechtigungen zugewiesen sein, bevor Sie diese Schritte ausführen können. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie im Thema zu den [Berechtigungen für Exchange-und Shell-Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten können, finden Sie unter [Tastenkombinationen im Exchange Admin Center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Konfigurieren der Integration zwischen Exchange Server und Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Schritt 1: Konfigurieren der OAuth-Authentifizierung zwischen Exchange Server und Office 365

Führen Sie die im folgenden Artikel aufgeführten Schritte aus:

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Schritt 2: Erstellen eines neuen e-Mail-Benutzerkontos für die Skype for Business Online-oder Team Partner-Anwendung

Dieser Schritt erfolgt auf dem Exchange-Server. Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen. Dieses Konto wird anschließend im nächsten Schritt gebraucht.

Geben Sie eine verifizierte Domäne für Ihre Exchange-Organisation an. Diese Domäne sollte dieselbe Domäne sein wie die primäre SMTP-Domäne, die für die lokalen Exchange-Konten verwendet wird. Diese Domäne wird im folgenden \<Verfahren als Ihre\> überprüfte Domäne bezeichnet. Außerdem sollte der \<DomainControllerFQDN\> der FQDN eines Domänencontrollers sein.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Schritt 3: Erstellen und Aktivieren einer Partner Anwendung für Skype for Business Online oder Teams

Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben. Führen Sie den folgenden Befehl in der Exchange-PowerShell in Ihrer lokalen Exchange-Organisation aus.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Überprüfen Ihres Erfolgs

Überprüfen Sie, ob die Konfiguration korrekt ist, indem Sie sicherstellen, dass einige Features erfolgreich funktionieren. 

1. Bestätigen Sie, dass die Outlook-Kalender Delegierung betweeen zwei Teams-Benutzer mit Exchange Server 2016-oder 2019-Postfächern funktioniert.

2. Der Konversations Verlauf für mobile Clients bestätigen ist im Outlook-Ordner "Konversations Verlauf" sichtbar.

Schauen Sie sich alternativ Ihren Traffic an. Der Datenverkehr in einem OAuth-Handshake ist wirklich charakteristisch (und sieht nicht wie die Standardauthentifizierung aus), insbesondere im Bereich der Realms, wo Sie beginnen, den Emittenten-Traffic zu sehen, der wie folgt aussieht: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit a/before das @-Zeichen) in den Token, die übergeben werden. Sie sehen keinen Benutzernamen oder kein Kennwort, was der OAuth-Punkt ist. Sie sehen aber den Aussteller "Office" – in diesem Fall "4" ist Skype for Business – und das Reich Ihres Abonnements.

Wenn Sie sicher sein möchten, dass Sie OAuth erfolgreich verwenden, stellen Sie sicher, dass Sie wissen, was Sie erwarten und wissen, wie der Datenverkehr aussehen soll. Hier [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)sehen Sie also ein ziemlich Standard [Beispiel für OAuth-Datenverkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (wirklich hilfreich zum Lesen, obwohl es keine Aktualisierungs Tokens verwendet), und es gibt Fiddler-Erweiterungen, mit denen Sie Ihre OAuth-JWT (JSON Web-Token).

Hier ist ein [Beispiel für die Einrichtung](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), aber Sie können jedes Netzwerk-Tracing-Tool verwenden, mit dem Sie diesen Prozess durchführen möchten.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
