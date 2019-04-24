---
title: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach dem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Zugriff aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199884"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation

Nach dem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Zugriff aktivieren, die für Ihre Organisation unterstützt werden.

Standardmäßig sind keine Richtlinien so konfiguriert, dass die Unterstützung der Zugriff durch externe Benutzer, einschließlich des Zugriffs durch Remotebenutzer, Verbundbenutzer Zugriff, selbst wenn Sie bereits Access-Unterstützung externer Benutzer für Ihre Organisation aktiviert haben. Um die Verwendung der Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien, konfigurieren und dabei die Art der Zugriff durch externe Benutzer für jede Richtlinie unterstützt. Die folgenden Richtlinienbereichen stehen für die Erstellung und Konfiguration. Standardmäßig die globale Richtlinie wird erstellt, aber kann nicht gelöscht werden.

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Edgeserver bereitstellen. Standardmäßig sind keine Access-Optionen für externe Benutzer in der globalen Richtlinie aktiviert. Zur Unterstützung der Zugriff durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie, um eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützen. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, jedoch Standortrichtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, Sie ihn nicht entfernen. Stattdessen müssen Sie Sie sie auf die Standardeinstellung.

  - **Site-Richtlinie**   Sie erstellen und konfigurieren Sie eine können oder weitere Richtlinien zur Begrenzung für externe Benutzerzugriff auf bestimmte Websites unterstützen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie in der globalen Richtlinie Zugriff durch Remotebenutzer aktivieren, können Sie beispielsweise eine Standortrichtlinie angeben, die Zugriff durch Remotebenutzer für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer dieser Website angewendet, jedoch können Sie eine Benutzerrichtlinie für einen Benutzer die Website-Einstellung außer Kraft gesetzt zuweisen.

  - **Benutzerrichtlinie**   können Sie erstellen und konfigurieren Sie eine oder mehrere Richtlinien für Benutzer beschränken für Remotebenutzerzugriff auf bestimmte Benutzer unterstützen. Die Konfiguration in der Benutzer außer Kraft setzt die globale und Richtlinien für den Standort, jedoch nur für bestimmte Benutzer, die die Richtlinie zugewiesen ist. Wenn Sie in der globalen Richtlinie und Standortrichtlinie Zugriff durch Remotebenutzer aktivieren, können Sie beispielsweise geben eine Benutzerrichtlinie, die Zugriff durch Remotebenutzer deaktiviert und weisen Sie diese Richtlinie auf bestimmte Benutzer. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie es an einen oder mehrere Benutzer anwenden, bevor sie wirksam wird.


> [!IMPORTANT]  
> Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


Zu diesen Optionen gehören die folgenden Typen von externen Zugriff:

  - **Kommunikation mit Partnerbenutzern aktivieren**   aktivieren Sie diese Option, wenn Sie Benutzerzugriff auf verbundpartnerdomänen unterstützen möchten. Diese Einstellung wird die Möglichkeit für Benutzer mit anderen kommunizieren, dass die SIP-Domänen als auch von gehosteten Anbietern wie Microsoft Office 365 federated konfiguriert. 


  - **Kommunikation mit Remotebenutzern aktivieren**   aktivieren Sie diese Option aus, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die außerhalb der Firewall, wie Telearbeiter und Benutzer, die viel unterwegs sind Skype für Business Server über das Internet herstellen können, sind.

  - **Aktivieren der Kommunikation mit Benutzern öffentlicher**   aktivieren Sie diese Option aus, wenn Sie möchten, dass interne Benutzer mit öffentlichen IM-Anbieter-Kontakten kommunizieren können.
   

> [!NOTE]  
> Neben der Aktivierung Zugriff durch externe Benutzer unterstützen, müssen Sie auch konfigurieren, Richtlinien zur Steuerung der Verwendung der Zugriff durch externe Benutzer in Ihrer Organisation, bevor keinerlei Zugriff durch externe Benutzer für Benutzer verfügbar ist. Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff externer Benutzer finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).



**So zeigen Sie Richtlinien für externen Zugriff mithilfe von Windows PowerShell-cmdlets**

  - Sie können Richtlinien für externen Zugriff mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Get-CsExternalAccessPolicy** anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. 
    
    Zum Anzeigen von Informationen über Ihre externe Zugriffsrichtlinien Geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
    `Get-CsExternalAccessPolicy`
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
