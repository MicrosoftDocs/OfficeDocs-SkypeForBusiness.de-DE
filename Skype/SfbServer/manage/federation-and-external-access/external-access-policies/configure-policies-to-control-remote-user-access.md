---
title: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Konfigurieren Sie einen oder mehrere externe Benutzer Zugriffsrichtlinien zur Steuerung können, ob Remotebenutzer mit internen Skype für Business Server-Benutzer zusammenarbeiten können. Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren.
ms.openlocfilehash: f6d316f022e671bc7f7e70ebbe2a801b0b3e312c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199891"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Skype für Business Server

Konfigurieren Sie einen oder mehrere externe Benutzer Zugriffsrichtlinien zur Steuerung können, ob Remotebenutzer mit internen Skype für Business Server-Benutzer zusammenarbeiten können. Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren. Websiterichtlinien außer Kraft setzen die globale Richtlinie, und Benutzerrichtlinien überschreiben, Website- und globale Richtlinien. Ausführliche Informationen zu den Arten von Richtlinien, die Sie konfigurieren können, finden Sie unter [Managing Federation und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md). Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

> [!NOTE]  
> Sie können Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer, konfigurieren, auch wenn Sie nicht Zugriff durch Remotebenutzer für Ihre Organisation aktiviert haben. Die Richtlinien, die Sie konfigurieren, werden jedoch in Kraft nur, wenn Sie den Zugriff durch Remotebenutzer für Ihre Organisation aktiviert haben. Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs durch Remotebenutzer angeben, gilt die Richtlinie darüber hinaus nur für Benutzer, die für Skype für Business Server aktiviert und so konfiguriert, dass die Richtlinie verwenden. Weitere Informationen zum Angeben der Benutzer, die sich bei Skype für Business Server von Remotestandorten aus anmelden können, finden Sie unter [Zuweisen eine Richtlinie für den externen Benutzerzugriff](assign-an-external-user-access-policy.md).

Verwenden Sie das folgende Verfahren jede Richtlinie für den externen Zugriff konfigurieren, die Sie zum Steuern des Zugriffs durch Remotebenutzer verwenden möchten.


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie so konfigurieren Sie eine Richtlinie nur zur Kommunikation mit Remotebenutzern aktivieren, aber jede Richtlinie, die Sie zur Unterstützung des Zugriffs durch Remotebenutzer konfigurieren kann auch partnerbenutzerzugriff und den Zugriff durch öffentliche Benutzer konfigurieren. Ausführliche Informationen zum Konfigurieren von Richtlinien, um Verbundbenutzer zu unterstützen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Benutzerzugriffs in Skype für Business Server federated](configure-policies-to-control-federated-user-access.md). Ausführliche Informationen zum Konfigurieren von Richtlinien, um öffentliche Benutzer unterstützen finden Sie unter [Verwalten von SIP-verbundanbietern für Ihre Organisation in Skype für Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>So konfigurieren Sie eine externe Zugriffsrichtlinie zur Unterstützung des Zugriffs durch Remotebenutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** eine der folgenden Aktionen aus:
    
      - Um die globale Richtlinie zur Unterstützung des Zugriffs durch Remotebenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
      - Erstellen einer neuen Standortrichtlinie, klicken Sie auf **neu**, und klicken Sie dann auf **Standortrichtlinie**. Klicken Sie im **Dialogfeld Standort auswählen**auf den geeigneten Standort aus der Liste aus, und klicken Sie dann auf **OK**.
    
      - Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in **Neue Richtlinie für den externen Zugriff**einen eindeutigen Namen im Feld **Name** , das angibt, welche Benutzer Richtlinie Hintergrund (beispielsweise **EnableRemoteUsers** für eine Benutzerrichtlinie, die die Kommunikation für Remotebenutzer ermöglicht).
    
      - Um eine vorhandene Richtlinie zu ändern, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  (Optional) Wenn Sie hinzufügen oder bearbeiten eine Beschreibung möchten, geben Sie die Informationen für die Richtlinie im Feld **Beschreibung**.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Um den Zugriff durch Remotebenutzer für die Richtlinie zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Zugriff durch Remotebenutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Um den Zugriff durch Remotebenutzer aktivieren, müssen Sie auch Unterstützung für den Zugriff durch Remotebenutzer in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Ist dies eine Benutzerrichtlinie, müssen Sie auch die Richtlinie für Benutzer anwenden, die Sie eine Remoteverbindung herstellen können möchten. Weitere Informationen hierzu finden Sie unter [Zuweisen eine Richtlinie für den externen Benutzerzugriff](assign-an-external-user-access-policy.md).
