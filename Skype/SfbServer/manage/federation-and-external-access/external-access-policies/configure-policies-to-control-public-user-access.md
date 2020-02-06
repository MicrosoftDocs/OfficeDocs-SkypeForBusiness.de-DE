---
title: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: UBLIC Instant Messaging (im)-Konnektivität ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Chat Dienstanbietern bereitgestellt werden.
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818306"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zum Steuern des Zugriffs von öffentlichen Benutzern in Skype for Business Server

Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Chatdienst Anbietern bereitgestellt werden. Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob öffentliche Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können. Die öffentliche Instant Messaging-Konnektivität ist ein hinzugefügtes Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert. Sie hängt auch von der Bereitstellung des Diensts beim öffentlichen Chat Dienstanbieter ab. 

Wenn Sie den Zugriff durch öffentliche Benutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren. Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

Im Fall von Chat-Einladungen hängt die Antwort von der Client Software ab. Die Anforderung wird akzeptiert, es sei denn, externe Absender werden explizit durch eine vom Benutzer konfigurierte Regel blockiert (also die Einstellungen in den Client- **Allow** -und- **Block** Listen). Darüber hinaus können Chat-Einladungen blockiert werden, wenn ein Benutzer wählt, Alle Chatnachrichten von Benutzern zu blockieren, die nicht in der **Zulassungs** Liste aufgeführt sind.



> [!NOTE]  
> Sie können Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer konfigurieren, auch wenn Sie die Föderation für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist. Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md). Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Details zum Angeben von öffentlichen Benutzern, die sich bei Skype for Business Server anmelden können, finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer](assign-an-external-user-access-policy.md).


Gehen Sie wie folgt vor, um eine Richtlinie zum unterstützen des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Chat Anbieter zu konfigurieren.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Zugriffs durch öffentliche Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:
    
      - Wenn Sie die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnablePublicUsers** für eine Benutzerrichtlinie, die die Kommunikation für öffentliche Benutzer aktiviert).
    
      - Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Wenn Sie den Zugriff durch öffentliche Benutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in Skype for Business Server](configure-policies-to-control-federated-user-access.md).

Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die in der Lage sein sollen, mit öffentlichen Benutzern zusammenzuarbeiten. 


## <a name="see-also"></a>Siehe auch

[Verwalten von SIP-Partnerverbundanbietern für eine Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
