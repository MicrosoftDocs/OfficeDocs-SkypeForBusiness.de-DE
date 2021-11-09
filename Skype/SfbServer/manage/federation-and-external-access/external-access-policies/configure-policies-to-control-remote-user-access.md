---
title: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Sie konfigurieren eine oder mehrere Zugriffsrichtlinien für externe Benutzer, um zu steuern, ob Remotebenutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren.
ms.openlocfilehash: a060622919fb8d948b55178a8e0b1d4da8b6e5cc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847288"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server

Sie konfigurieren eine oder mehrere Zugriffsrichtlinien für externe Benutzer, um zu steuern, ob Remotebenutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren. Standortrichtlinien setzen die globale Richtlinie außer Kraft, und Benutzerrichtlinien setzen Standort- und globale Richtlinien außer Kraft. Ausführliche Informationen zu den Typen von Richtlinien, die Sie konfigurieren können, finden Sie unter [Verwalten des Partnerverbunds und des externen Zugriffs auf Skype for Business Server.](../managing-federation-and-external-access.md) Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.

> [!NOTE]  
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer konfigurieren, wenn Sie den Zugriff durch Remotebenutzer für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst in Kraft, wenn der Zugriff durch Remotebenutzer für Ihre Organisation aktiviert wird. Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Remotebenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Ausführliche Informationen zum Angeben von Benutzern, die sich von Remotestandorten aus bei Skype for Business Server anmelden können, finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer.](assign-an-external-user-access-policy.md)

Führen Sie die folgenden Schritte aus, um die einzelnen Richtlinien für den externen Zugriff zu konfigurieren, die zur Steuerung des Remotebenutzerzugriffs verwendet werden sollen.


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie eine Richtlinie nur so konfiguriert wird, dass die Kommunikation mit Remotebenutzern aktiviert wird. Jede Richtlinie, die Sie zur Unterstützung des Remotebenutzerzugriffs konfigurieren, kann jedoch auch den Verbundbenutzerzugriff und den öffentlichen Benutzerzugriff konfigurieren. Ausführliche Informationen zum Konfigurieren von Richtlinien zur Unterstützung von Verbundbenutzern finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Verbundbenutzerzugriffs in Skype for Business Server.](configure-policies-to-control-federated-user-access.md) Ausführliche Informationen zum Konfigurieren von Richtlinien zur Unterstützung öffentlicher Benutzer finden Sie unter [Verwalten von SIP-Verbundanbietern für Ihre Organisation in Skype for Business Server.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Remotebenutzer

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch Remotebenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableRemoteUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Remotebenutzer ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren**, um den Zugriff durch Remotebenutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren**, um den Zugriff durch Remotebenutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit**.

Um den Zugriff durch Remotebenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Remotebenutzerzugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter Aktivieren oder Deaktivieren des [Partnerverbunds und der Verbindung mit öffentlichen Chatdiensten.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, für die Sie eine Remoteverbindung zulassen möchten. Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer.](assign-an-external-user-access-policy.md)
