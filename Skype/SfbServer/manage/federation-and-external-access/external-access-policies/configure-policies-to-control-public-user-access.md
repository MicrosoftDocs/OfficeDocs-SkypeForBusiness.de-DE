---
title: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Die chatbasierte Chatkonnektivität ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chatnachrichten, um mit Benutzern von Chatdiensten zu kommunizieren, die von öffentlichen Chatdienstanbietern bereitgestellt werden.
ms.openlocfilehash: b5c7d75a6048a584fcb872ed8eb3cd82dfe2076f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847308"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zum Steuern des öffentlichen Benutzerzugriffs in Skype for Business Server

Die Verbindung mit öffentlichen Chatnachrichten ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chatnachrichten, um mit Benutzern von Chatdiensten zu kommunizieren, die von öffentlichen Chatdienstanbietern bereitgestellt werden. Sie konfigurieren eine oder mehrere Zugriffsrichtlinien für externe Benutzer, um zu steuern, ob öffentliche Benutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können. Die Verbindung mit öffentlichen Chatnachrichten ist ein zusätzliches Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert. Es hängt auch von der Bereitstellung des Diensts beim öffentlichen Chatanbieter ab. 

Zum Steuern des Zugriffs durch öffentliche Benutzer können Sie Richtlinien auf globaler Ebene und Standort- und Benutzerebene konfigurieren. Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.

Im Fall von Sofortnachrichten-Einladungen hängt die Antwort von der Clientsoftware ab. Die Anforderung wird akzeptiert, sofern externe Absender nicht ausdrücklich durch eine vom Benutzer konfigurierte Regel (also Einstellungen in der **Zulassungs-** und **Blockierliste** des Benutzers) blockiert werden. Darüber hinaus können Sofortnachrichten-Einladungen blockiert werden, wenn ein Benutzer festlegt, dass alle Sofortnachrichten von Benutzern, die nicht in der **Zulassungsliste** enthalten sind, blockiert werden.



> [!NOTE]  
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch öffentliche Benutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs.](../access-edge/enable-or-disable-remote-user-access.md) Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des öffentlichen Benutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Ausführliche Informationen zum Angeben öffentlicher Benutzer, die sich bei Skype for Business Server anmelden können, finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer.](assign-an-external-user-access-policy.md)


Gehen Sie folgendermaßen vor, um eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Sofortnachrichtenanbieter zu konfigurieren.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch öffentliche Benutzer

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnablePublicUsers** für eine Benutzerrichtlinie, welche die Kommunikation für öffentliche Benutzer ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit**.

Um den Zugriff durch öffentliche Benutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Verbundbenutzerzugriffs in Skype for Business Server.](configure-policies-to-control-federated-user-access.md)

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die mit öffentlichen Benutzern zusammenarbeiten sollen. 


## <a name="see-also"></a>Siehe auch

[Verwalten von SIP-Partnerverbundanbietern für eine Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
