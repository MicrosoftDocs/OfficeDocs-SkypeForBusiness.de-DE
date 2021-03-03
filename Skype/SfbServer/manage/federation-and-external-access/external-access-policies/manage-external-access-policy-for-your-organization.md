---
title: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817255"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation

Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.

In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.

  - **Globale Richtlinie**   Die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert. Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt. Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie**   Sie können eine oder mehrere Websiterichtlinien erstellen und konfigurieren, um die Unterstützung für den externen Benutzerzugriff auf bestimmte Websites zu beschränken. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Remotebenutzerzugriff auf bestimmte Benutzer zu beschränken. Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.


> [!IMPORTANT]  
> Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.


Diese Optionen umfassen die folgenden Arten des externen Zugriffs:

  - **Aktivieren der Kommunikation mit Verbundbenutzern**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Verbundpartnerdomänen unterstützen möchten. Mit dieser Einstellung wird die Möglichkeit konfiguriert, dass Benutzer mit anderen SIP-Verbunddomänen sowie gehosteten Anbietern wie Microsoft 365 oder Office 365 kommunizieren können. 


  - **Aktivieren der Kommunikation mit Remotebenutzern**   Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, z. B. Telekommunikationsanbieter und Benutzer, die unterwegs sind, über das Internet eine Verbindung mit Skype for Business Server herstellen können sollen.

  - **Aktivieren der Kommunikation mit öffentlichen Benutzern**   Aktivieren Sie diese Option, wenn interne Benutzer mit Kontakten des öffentlichen Anbieters für Automatische Dienstleistungen kommunizieren können sollen.
   

> [!NOTE]  
> Neben dem Aktivieren der Unterstützung für den externen Benutzerzugriff müssen Sie auch Richtlinien konfigurieren, um die Verwendung des externen Benutzerzugriffs in Ihrer Organisation zu steuern, bevor den Benutzern ein beliebiger Typ des externen Benutzerzugriffs zur Verfügung steht. Ausführliche Informationen zur Erstellung, Konfiguration und Anwendung von Richtlinien für den externen Benutzerzugriff finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).



**So zeigen Sie Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**

  - Sie können Richtlinien für den externen Zugriff mit der Skype for Business Server-Verwaltungsshell und dem Cmdlets **Get-CsExternalAccessPolicy** anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. 
    
    Um Informationen über alle Richtlinien für den externen Zugriff anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
    `Get-CsExternalAccessPolicy`
    
    Es werden etwa folgende Informationen zurückgegeben:
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
