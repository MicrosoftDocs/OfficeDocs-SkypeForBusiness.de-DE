---
title: Verwalten vertrauenswürdiger Anwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151225"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Verwalten vertrauenswürdiger Anwendungen in Skype for Business Server

Eine *vertrauenswürdige Anwendung* ist eine Anwendung, die auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3,0 Core SDK Documentation https://go.microsoft.com/fwlink/p/?linkId=210320" unter.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. 

In diesem Artikel erfahren Sie, wie Sie einen neuen vertrauenswürdigen Anwendungsserver konfigurieren, eine Liste vertrauenswürdiger Anwendungen anzeigen und vertrauenswürdige Anwendungsinformationen anzeigen können. 

## <a name="configure-a-new-trusted-application-server"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topologie-Generator**.

3.  Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld **Topologie speichern** unter auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.

5.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **neuer vertrauenswürdiger Anwendungs Pool**.

6.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen Einzelserver oder mehrere Server handelt, und klicken Sie dann auf **weiter**.

7.  Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die Skype for Business Server Front-End-Pool aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten **Skype for Business Server**aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.
    
    Der **Vertrauenswürdige Anwendungs Pool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet werden.


## <a name="view-a-list-of-trusted-applications"></a>Anzeigen einer Liste vertrauenswürdiger Anwendungen

Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in Ihrer Skype for Business Server Umgebung bereitgestellt haben. Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird. Die Eigenschaften dieser Vertrauensbeziehung werden in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden nicht für die Authentifizierung durch Skype for Business Server herausgefordert.

  - Vertrauenswürdige Anwendungen werden nicht durch Skype for Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.

  - Vertrauenswürdige Anwendungen können die Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in Konferenzlisten aufzutauchen.

  - Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.

In der Skype for Business Server-Systemsteuerung werden der Name der Anwendungen, der Pool, in dem Sie ausgeführt werden, und der verwendete Port angezeigt.


### <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an

1.  Melden Sie sich über ein Benutzerkonto, das der CsServerAdministrator-, CsAdministrator-, "cshelpdesk"-oder CsViewOnlyAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an. Ausführliche Informationen zu den in Skype for Business Server verfügbaren vordefinierten Administratorrollen finden Sie unter [Role-Based Access Control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und klicken Sie dann auf **vertrauenswürdige Anwendung**.

4.  Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.


## <a name="view-trusted-application-information"></a>Anzeigen von Informationen zu vertrauenswürdigen Anwendungen

Sie können Informationen zu vertrauenswürdigen Anwendungen mit Windows PowerShell und dem Cmdlet **Get-CsTrustedApplication** anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


### <a name="to-view-trusted-applications"></a>So zeigen Sie vertrauenswürdige Anwendungen an

Um alle vertrauenswürdigen Anwendungen anzuzeigen, geben Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
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
