---
title: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen oder mehrere Edge-Server bereitgestellt haben, müssen Sie die Typen des externen Zugriffs aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: 014077fb331bc33933d0c673771f7765b9341570
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280117"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation

Nachdem Sie einen oder mehrere Edge-Server bereitgestellt haben, müssen Sie die Typen des externen Zugriffs aktivieren, die für Ihre Organisation unterstützt werden.

Standardmäßig sind keine Richtlinien zur Unterstützung des Zugriffs externer Benutzer, einschließlich des Remotebenutzerzugriffs, des Zugriffs auf den Verbundbenutzer konfiguriert, auch wenn Sie die Unterstützung für den externen Benutzer Zugriff für Ihre Organisation bereits aktiviert haben. Um die Verwendung des Zugriffs auf externe Benutzer zu steuern, müssen Sie eine oder mehrere Richtlinien konfigurieren und den Typ des für jede Richtlinie unterstützten externen Benutzerzugriffs angeben. Die folgenden Richtlinienbereiche stehen für die Erstellung und Konfiguration zur Verfügung. Standardmäßig wird die globale Richtlinie erstellt, kann aber nicht gelöscht werden.

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind keine Optionen für den externen Benutzer Zugriff in der globalen Richtlinie aktiviert. Zur Unterstützung des Zugriffs externer Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützt werden. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, aber Website Richtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, werden Sie nicht entfernt. Stattdessen setzen Sie Sie auf die Standardeinstellung zurück.

  - **Website Richtlinie**   Sie können eine oder mehrere Website Richtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff externer Benutzer auf bestimmte Websites zu begrenzen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, geben Sie möglicherweise eine Website Richtlinie an, die den Remotebenutzerzugriff für eine bestimmte Website deaktiviert. Standardmäßig wird eine Website Richtlinie auf alle Benutzer dieser Website angewendet, aber Sie können einem Benutzer eine Benutzerrichtlinie zuweisen, um die Website Richtlinieneinstellung zu überschreiben.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer zu begrenzen. Die Konfiguration in der Benutzerrichtlinie überschreibt die globale und die Website Richtlinie, jedoch nur für bestimmte Benutzer, denen die Benutzerrichtlinie zugewiesen ist. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und der Website Richtlinie aktivieren, geben Sie möglicherweise eine Benutzerrichtlinie an, die den Zugriff durch Remotebenutzer deaktiviert und diese Benutzerrichtlinie dann bestimmten Benutzern zuweist. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie Sie auf einen oder mehrere Benutzer anwenden, bevor Sie wirksam wird.


> [!IMPORTANT]  
> Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


Zu diesen Optionen gehören die folgenden Typen von externem Zugriff:

  - **Aktivieren der Kommunikation mit Verbundbenutzern**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten. Diese Einstellung konfiguriert die Möglichkeit für Benutzer, mit anderen SIP-Verbunddomänen sowie gehosteten Anbietern wie Microsoft Office 365 zu kommunizieren. 


  - **Aktivieren der Kommunikation mit Remotebenutzern**   aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit Skype for Business Server über das Internet herstellen können.

  - **Aktivieren der Kommunikation mit öffentlichen Benutzern**   aktivieren Sie diese Option, wenn interne Benutzer in der Lage sein sollen, mit öffentlichen Chat-Anbieter Kontakten zu kommunizieren.
   

> [!NOTE]  
> Neben der Unterstützung für den Zugriff durch externe Benutzer müssen Sie auch Richtlinien konfigurieren, um die Verwendung des Zugriffs externer Benutzer in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten. Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md).



**So zeigen Sie die Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**

  - Sie können die Richtlinien für den externen Zugriff mit der Skype for Business Server-Verwaltungsshell und dem Cmdlet **Get-CsExternalAccessPolicy** anzeigen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. 
    
    Wenn Sie Informationen zu allen Ihren externen Zugriffsrichtlinien anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
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
