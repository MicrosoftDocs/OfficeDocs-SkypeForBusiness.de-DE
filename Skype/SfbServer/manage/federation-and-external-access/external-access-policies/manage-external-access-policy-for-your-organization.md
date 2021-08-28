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
ms.localizationpriority: medium
description: Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.
ms.openlocfilehash: acd69cf74d6e7a17265543fb326f279b3bc3360f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582749"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation

Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.

In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.

  - **Globale Richtlinie**: Diese Richtlinie wird erstellt, wenn Sie Ihre Edge-Server bereitstellen. Optionen für den Zugriff durch externe Benutzer sind in der globalen Richtlinie zunächst nicht aktiviert. Um den Zugriff durch externe Benutzer auf globaler Ebene zu unterstützen, konfigurieren Sie die entsprechende Richtlinie, sodass eine oder mehrere Optionen für den Zugriff durch externe Benutzer unterstützt werden. Die globale Richtlinie wird für alle Benutzer in der Organisation verwendet. Sie kann jedoch durch Standortrichtlinien und Benutzerrichtlinien überschrieben werden. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt, sondern auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie**   Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch externe Benutzer auf bestimmte Standorte einzuschränken. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer einzuschränken. Die Konfiguration in der Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird. Wenn Sie beispielsweise den Zugriff durch Remotebenutzer in der globalen und in der Standortrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Zugriff durch Remotebenutzer deaktiviert. Anschließend können Sie diese Benutzerrichtlinie bestimmten Benutzern zuweisen. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie sie auf einen oder mehrere Benutzer anwenden, damit sie wirksam wird.


> [!IMPORTANT]  
> Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.


Diese Optionen umfassen die folgenden Arten des externen Zugriffs:

  - **Aktivieren der Kommunikation mit Verbundbenutzern**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Partnerdomänen unterstützen möchten. Diese Einstellung konfiguriert die Möglichkeit für Benutzer, mit anderen SIP-Verbunddomänen sowie mit gehosteten Anbietern wie Microsoft 365 oder Office 365 zu kommunizieren. 


  - **Aktivieren der Kommunikation mit Remotebenutzern**   Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, z. B. Telekommunikationspendler und Benutzer, die unterwegs sind, in der Lage sein sollen, eine Verbindung mit Skype for Business Server über das Internet herzustellen.

  - **Aktivieren der Kommunikation mit öffentlichen Benutzern**   Aktivieren Sie diese Option, wenn interne Benutzer mit Kontakten des öffentlichen Chatanbieters kommunizieren können sollen.
   

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
