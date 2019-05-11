---
title: Verwalten von vertrauenswürdigen Anwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine vertrauenswürdige Anwendung ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut.
ms.openlocfilehash: 0f483cc0a1a3a9e7dad881fc40819a9c27dacdec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911868"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Verwalten von vertrauenswürdigen Anwendungen in Skype für Business Server

Eine *Vertrauenswürdige Anwendung* ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut. Ausführliche Informationen über UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3.0 Core SDK-Dokumentation" unter http://go.microsoft.com/fwlink/p/?linkId=210320.

Erfolgreich veröffentlichen, aktivieren oder Deaktivieren einer Topologie, die beim Hinzufügen oder Entfernen einer Serverrolle, sollten Sie als ein Benutzer ein Mitglied der Gruppen RTCUniversalServerAdmins und Domänen-Admins angemeldet sein. 

Verwenden Sie diesen Artikel, um Informationen zum Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers, zeigen Sie eine Liste der vertrauenswürdigen Anwendungen und vertrauenswürdige Anwendungsinformationen anzeigen. 

## <a name="configure-a-new-trusted-application-server"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.

3.  Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld **Topologie speichern unter** klicken Sie auf der Topologie-Generator-Datei, den, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.

5.  Klicken Sie im linken Bereich Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **Neuer Pool für vertrauenswürdige Anwendung**.

6.  Geben Sie den **FQDN des Pools** für den vertrauenswürdigen Anwendungspool auswählen, ob sie einen einzelnen oder mehreren Servern werden, und klicken Sie dann auf **Weiter**.

7.  Wählen Sie auf der Seite **Wählen Sie den nächsten Hop** aus der Liste der Skype für Business Server-Front-End-Pool ein.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten **Skype für Business Server**aus, und klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**.
    
    Wurde sollte der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet.


## <a name="view-a-list-of-trusted-applications"></a>Anzeigen einer Liste der vertrauenswürdigen Anwendungen

Sie können die Skype Business Server-Systemsteuerung verwenden, zum Anzeigen einer Liste der vertrauenswürdigen Anwendungen, die Sie in Ihre Skype für Business Server-Umgebung bereitgestellt haben. Eine vertrauenswürdige Anwendung ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut. Diese Vertrauensstellung ist in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden nicht für die Authentifizierung von Skype für Business Server angefordert.

  - Vertrauenswürdige Anwendungen werden nicht von Skype für Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP over Internet Protocol (VoIP) anrufen weder gedrosselt.

  - Vertrauenswürdige Anwendungen können Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in konferenzlisten aufzutauchen.

  - Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.

In der Skype Business Server-Systemsteuerung sehen Sie den Namen der Anwendungen, den Pool für deren Ausführung und den Port, die, den Sie verwenden.


### <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Ausführliche Informationen zu den vordefinierten Administratorrollen in Skype für Business Server verfügbar sind finden Sie unter [Role-based Access Control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und klicken Sie dann auf **Vertrauenswürdige Anwendung**.

4.  Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen zu sortieren, bei Bedarf.


## <a name="view-trusted-application-information"></a>Anzeigen von Informationen für vertrauenswürdige Anwendung

Sie können Informationen zu vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell und das Cmdlet **Get-CsTrustedApplication** anzeigen. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 


### <a name="to-view-trusted-applications"></a>So zeigen Sie vertrauenswürdige Anwendungen an

Um alle vertrauenswürdigen Anwendung anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsConferenceDisclaimer
    
   Mit diesem Befehl werden Informationen ähnlich dem folgenden für jede vertrauenswürdige Anwendung zurückgegeben:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   Weitere Informationen hierzu finden Sie unter [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
