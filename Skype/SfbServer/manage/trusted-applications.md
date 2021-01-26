---
title: Verwalten vertrauenswürdiger Anwendungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf der Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826275"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Verwalten von vertrauenswürdigen Anwendungen in Skype for Business Server

Eine *vertrauenswürdige Anwendung* ist eine Anwendung, die auf der Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3.0 Core SDK Documentation" unter https://go.microsoft.com/fwlink/p/?linkId=210320 .

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. 

In diesem Artikel erfahren Sie, wie Sie einen neuen vertrauenswürdigen Anwendungsserver konfigurieren, eine Liste vertrauenswürdiger Anwendungen anzeigen und Informationen zu vertrauenswürdigen Anwendungen anzeigen. 

## <a name="configure-a-new-trusted-application-server"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie **auf "Start",**"Alle Programme",  **"Skype for Business Server"** und dann auf **"Skype for Business Server-Topologie-Generator".**

3.  Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.

4.  Klicken Sie **im Dialogfeld "Topologie** speichern unter" auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **"Speichern".**

5.  Klicken Sie im linken Bereich mit der rechten Maustaste **auf** vertrauenswürdige Anwendungsserver, und klicken Sie dann auf **"Neuer Pool vertrauenswürdiger Anwendungen".**

6.  Geben Sie **den Pool-FQDN** des Pools mit vertrauenswürdigen Anwendungen ein, wählen Sie aus, ob es sich um einen einzelnen Oder mehrere Server und dann auf **"Weiter" (Weiter) aus.**

7.  Wählen Sie auf der Seite "Nächsten **Hop auswählen"** in der Liste den Skype for Business Server-Front-End-Pool aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten Skype for Business  **Server** aus, und klicken Sie dann im Menü "Aktionen" auf **"Topologie veröffentlichen".**
    
    Der **vertrauenswürdige Anwendungspool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet worden sein.


## <a name="view-a-list-of-trusted-applications"></a>Anzeigen einer Liste vertrauenswürdiger Anwendungen

Mithilfe der Skype for Business Server-Systemsteuerung können Sie eine Liste der vertrauenswürdigen Anwendungen anzeigen, die Sie in Ihrer Skype for Business Server-Umgebung bereitgestellt haben. Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf der Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird. Die Eigenschaften dieser Vertrauensbeziehung werden in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden nicht für die Authentifizierung durch Skype for Business Server in Frage gestellt.

  - Vertrauenswürdige Anwendungen werden von Skype for Business Server nicht für SIP-Transaktionen, Verbindungen oder ausgehende Voice over Internet Protocol (VoIP)-Anrufe gedrosselt.

  - Vertrauenswürdige Anwendungen können die Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in Konferenzlisten aufzutauchen.

  - Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.

In der Skype for Business Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem sie ausgeführt werden, und den verwendeten Port sehen.


### <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an

1.  Melden Sie sich mit einem Benutzerkonto, das der Rolle "CsServerAdministrator", "CsAdministrator", "CsHelpDesk" oder "CsViewOnlyAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an. Weitere Informationen zu den vordefinierten Administratorrollen, die in Skype for Business Server verfügbar sind, finden Sie unter Rollenbasierte Zugriffssteuerung [(ROLE-based Access Control, RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste **auf "Topologie"** und dann auf **"Vertrauenswürdige Anwendung".**

4.  Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.


## <a name="view-trusted-application-information"></a>Anzeigen von Informationen zu vertrauenswürdigen Anwendungen

Sie können Informationen zu Ihren vertrauenswürdigen Anwendungen mithilfe Windows PowerShell **cmdlets "Get-CsTrustedApplication"** anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>So zeigen Sie vertrauenswürdige Anwendungen an

Geben Sie zum Anzeigen aller vertrauenswürdigen Anwendungen den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsConferenceDisclaimer
    
   Mit diesem Befehl werden Informationen zu den einzelnen vertrauenswürdigen Anwendungen nach folgendem Muster zurückgegeben:
    
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
    
   Ausführliche Informationen finden Sie unter [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
