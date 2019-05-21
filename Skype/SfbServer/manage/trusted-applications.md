---
title: Verwalten vertrauenswürdiger Anwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275066"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Verwalten von vertrauenswürdigen Anwendungen in Skype for Business Server

Bei einer *vertrauenswürdigen Anwendung* handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3,0 Core SDK Documentation http://go.microsoft.com/fwlink/p/?linkId=210320" unter.

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. 

In diesem Artikel erfahren Sie, wie Sie einen neuen vertrauenswürdigen Anwendungsserver konfigurieren, eine Liste der vertrauenswürdigen Anwendungen anzeigen und vertrauenswürdige Anwendungsinformationen anzeigen können. 

## <a name="configure-a-new-trusted-application-server"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.

3.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld **Topologie speichern** unter auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.

5.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **neuer vertrauenswürdiger Anwendungs Pool**.

6.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen Einzelserver-oder mehrere Server handelt, und klicken Sie dann auf **weiter**.

7.  Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den Skype for Business Server-Front-End-Pool aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten **für Skype for Business Server**aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.
    
    Der **Vertrauenswürdige Anwendungspool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet sein.


## <a name="view-a-list-of-trusted-applications"></a>Anzeigen einer Liste vertrauenswürdiger Anwendungen

Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in Ihrer Skype for Business Server-Umgebung bereitgestellt haben. Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird. Diese Vertrauensstellung wird in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden von Skype for Business Server nicht für die Authentifizierung in Frage gestellt.

  - Vertrauenswürdige Anwendungen werden nicht von Skype for Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.

  - Vertrauenswürdige Anwendungen können sich als alle Benutzer erweisen und können an Konferenzen teilnehmen, ohne dass Sie in Dienstplänen angezeigt werden.

  - Vertrauenswürdige Anwendungen sind hochgradig verfügbar und widerstandsfähig.

In der Skype for Business Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem Sie ausgeführt werden, und den verwendeten Port sehen.


### <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste vertrauenswürdiger Anwendungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in Skype for Business Server zur Verfügung stehen, finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und klicken Sie dann auf **vertrauenswürdige Anwendung**.

4.  Klicken Sie auf der Seite **vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.


## <a name="view-trusted-application-information"></a>Anzeigen von Informationen zu vertrauenswürdigen Anwendungen

Sie können Informationen zu vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsTrustedApplication** anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


### <a name="to-view-trusted-applications"></a>So zeigen Sie vertrauenswürdige Anwendungen an

Wenn Sie alle vertrauenswürdigen Anwendungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsConferenceDisclaimer
    
   Dieser Befehl gibt für jede vertrauenswürdige Anwendung Informationen zurück, die der folgenden ähneln:
    
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
