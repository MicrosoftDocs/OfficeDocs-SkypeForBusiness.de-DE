---
title: Verwalten von SIP-Partnerdomänen für eine Organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Informationen zum Verwalten und Konfigurieren von SIP-Domänen, mit deren Verbund Sie einen Verbund erstellen können,
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817215"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Verwalten von SIP-Verbunddomänen für Ihre Organisation in Skype for Business Server


Wenn Sie SIP-Domänen verwalten und konfigurieren möchten, mit denen Sie einen Verbund einrichten können, haben Sie die folgenden Möglichkeiten:

  - Erstellen oder bearbeiten Sie eine Liste zulässiger Domänen für Partnerdomänen mit SIP-Verbund.

  - Erstellen oder bearbeiten Sie eine Liste blockierter Domänen für Domänen mit SIP-Verbund.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für zulässige externe Domänen in Skype for Business Server

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche spezifischen Domänen einen Partnerverbund mit Ihrer Organisation eingehen können. Konfigurieren Sie eine oder mehrere spezifische externe Domänen als zulässige Partnerdomänen. Fügen Sie hierzu jede Domäne der Liste zulässiger Domänen hinzu. Selbst wenn die Suche von Verbundpartnern für Ihre Organisation aktiviert ist, führen Sie diesen Schritt aus, wenn es sich bei der Domäne um einen Verbundpartner handelt, der mit mehr als 1.000 Ihrer Benutzer kommunizieren oder mehr als 20 Nachrichten pro Sekunde senden muss. Ist die Suche von Verbundpartnern für Ihre Organisation nicht aktiviert, können nur Benutzer aus externen Domänen am Instant Messaging und an Konferenzen mit Benutzern Ihrer Organisation teilnehmen, die Sie der Liste zulässiger Domänen hinzugefügt haben. Wenn Sie den Zugriff einer Partnerdomäne auf einen bestimmten Server beschränken möchten, auf dem der Zugriffs-Edgedienst des Verbundpartners ausgeführt wird, können Sie für jede Domäne in der Liste zulässiger Domänen den Domänennamen des Servers angeben, auf dem der Zugriffs-Edgedienst ausgeführt wird.

> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber für die Implementierung der Unterstützung für Verbundbenutzer müssen Sie auch die Unterstützung für Partnerbenutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer mit Verbundbenutzern zusammenarbeiten können. Weitere Informationen zum Aktivieren der Unterstützung für Partnerbenutzer finden Sie unter "Aktivieren oder Deaktivieren [des Remotebenutzerzugriffs".](../access-edge/enable-or-disable-remote-user-access.md) Weitere Informationen zum Konfigurieren von Richtlinien zur Steuerung des Partnerverbunds finden Sie unter "Konfigurieren von Richtlinien zum Steuern des [Zugriffs durch Partnerbenutzer".](../external-access-policies/configure-policies-to-control-federated-user-access.md)

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>So fügen Sie eine externe Domäne der Liste zulässiger Domänen hinzu

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Partnerdomänen**.
4.  Klicken Sie auf der Seite **Partnerdomänen** auf **Neu** und anschließend auf **Zulässige Domäne**.
5.  Führen Sie unter **Neue Partnerdomänen** die folgenden Aktionen aus:
    
      - Geben Sie unter **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein.       

        > [!NOTE]  
        > Dieser Name muss eindeutig sein und darf noch nicht als zulässige Domäne für diesen Server vorliegen, auf dem der Zugriffs-Edgedienst ausgeführt wird. Der Name darf höchstens 256 Zeichen lang sein.<BR><br>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise **contoso.com** eingeben, wird als Suchergebnis auch die Domäne **it.contoso.com** zurückgegeben.<BR><br>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Skype for Business Server verhindert dies, sodass Sie Ihre Listen nicht synchronisieren müssen.
    
      - Wenn Sie den Zugriff für diese Partnerdomäne auf Benutzer eines bestimmten Servers beschränken möchten, auf dem der Zugriffs-Edgedienst ausgeführt wird, geben Sie unter **Zugriffs-Edgedienst (FQDN)** den FQDN des Servers der Partnerdomäne ein, auf dem der Zugriffs-Edgedienst ausgeführt wird.    
      - Wenn Sie zusätzliche Informationen bereitstellen möchten, geben Sie unter **Kommentar** Informationen ein, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.

6.  Klicken Sie auf **Commit**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jede Verbundpartnerdomäne, die Sie zulassen möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer.](../access-edge/enable-or-disable-remote-user-access.md)

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Weitere Informationen finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des Zugriffs durch Partnerbenutzer".](../external-access-policies/configure-policies-to-control-federated-user-access.md)

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für blockierte externe Domänen in Skype for Business Server 

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche Domänen am Verbund mit Ihrer Organisation blockiert werden. Die Liste der blockierten Domänen wird als Sperrliste (Liste der expliziten Einträge, die nicht zulässig sind) und bei der Ermittlung von Verbunddomänen angewendet, wenn Sie diese Option aktiviert haben. Weitere Informationen finden Sie unter ["Aktivieren oder Deaktivieren der Suche von Verbundpartnern".](../access-edge/enable-or-disable-discovery-of-federation-partners.md)

Blockieren Sie eine oder mehrere externe Domänen vom Herstellen einer Verbindung mit Ihrer Organisation. Fügen Sie hierzu die Domäne der Liste blockierter Domänen hinzu.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>So fügen Sie der Liste blockierter Domänen eine externe Domäne hinzu

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**.
4.  Klicken Sie auf **Partnerdomänen**, auf **Neu** und dann auf **Blockierte Domäne**.
5.  Führen Sie unter **Neue Partnerdomänen** die folgende Aktion aus:
    
      - Geben Sie im Feld **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein, die blockiert werden soll.

        > [!NOTE]  
        > Der Name darf maximal 256 Zeichen umfassen.<BR><br>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise **contoso.com** eingeben, wird als Suchergebnis auch die Domäne **it.contoso.com** zurückgegeben.<BR><br>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Skype for Business Server verhindert dies, sodass Sie Ihre Listen nicht synchronisieren müssen.
   
      - Im Feld **Kommentar** können Sie Informationen zur Konfiguration eingeben, die Sie mit anderen Systemadministratoren teilen möchten. Dieses Feld ist optional.

6.  Klicken Sie auf **Commit**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Verbundpartner, den Sie blockieren möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer.](../access-edge/enable-or-disable-remote-user-access.md)

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Weitere Informationen finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des Zugriffs durch Partnerbenutzer".](../external-access-policies/configure-policies-to-control-federated-user-access.md)


## <a name="see-also"></a>Siehe auch

[Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Aktivieren oder Deaktivieren der Suche von Verbundpartnern](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

