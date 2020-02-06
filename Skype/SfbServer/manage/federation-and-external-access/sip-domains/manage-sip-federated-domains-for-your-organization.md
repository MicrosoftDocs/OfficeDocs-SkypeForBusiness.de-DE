---
title: Verwalten von SIP-Partnerdomänen für eine Organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Hier erfahren Sie, wie Sie SIP-Domänen verwalten und konfigurieren, mit denen Sie eine Föderation führen können.
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818236"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Verwalten von SIP-Verbunddomänen für Ihre Organisation in Skype for Business Server


Zum Verwalten und Konfigurieren von SIP-Domänen, mit denen Sie eine Föderation führen können, können Sie die folgenden Aktionen ausführen:

  - Erstellen oder bearbeiten Sie eine Liste der zulässigen Domänen der SIP-Partnerdomänen.

  - Erstellen oder Bearbeiten einer Liste blockierter Domänen mit SIP-Verbunddomänen

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für zugelassene externe Domänen in Skype for Business Server

Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche bestimmten Domänen mit Ihrer Organisation verbunden werden können. Sie konfigurieren eine oder mehrere bestimmte externe Domänen als zugelassene Verbunddomänen. Fügen Sie dazu jede Domäne zur Liste der zulässigen Domänen hinzu. Auch wenn die Partner Ermittlung für Ihre Organisation aktiviert ist, gehen Sie wie folgt vor, wenn es sich bei der Domäne um einen Verbundpartner handelt, der möglicherweise mit mehr als 1.000 ihrer Benutzer kommunizieren muss, oder wenn Sie möglicherweise mehr als 20 Nachrichten pro Sekunde senden müssen. Wenn die Partner Ermittlung für Ihre Organisation nicht aktiviert ist, können nur Benutzer externer Domänen, die Sie der Liste zugelassene Domänen hinzufügen, an Chats und Konferenzen mit Benutzern in Ihrer Organisation teilnehmen. Wenn Sie den Zugriff auf eine Verbunddomäne auf einen bestimmten Server einschränken möchten, auf dem der Access-Edgedienst des Verbundpartners ausgeführt wird, können Sie den Domänennamen des Servers angeben, auf dem der Access Edge-Dienst für jede Domäne in der Liste der zulässigen Domänen ausgeführt wird.

> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber die Implementierung der Unterstützung für verbundene Benutzer erfordert auch, dass Sie die Unterstützung für verbundene Benutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer Zusammenarbeit mit Verbundbenutzern. Details zum Aktivieren der Unterstützung für Verbundbenutzer finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md). Details zum Konfigurieren von Richtlinien für die Steuerung der Föderation finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>So fügen Sie eine externe Domäne zur Liste der zulässigen Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Föderationsdomänen**.
4.  Klicken Sie auf der Seite **Federated Domains** auf **neu**und dann auf **zugelassene Domäne**.
5.  Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:
    
      - Geben Sie in **Domänenname (oder FQDN)** den Namen der Föderationspartner-Domäne ein.       

        > [!NOTE]  
        > Dieser Name muss eindeutig sein und kann nicht bereits als zulässige Domäne für diesen Server mit dem Access Edge-Dienst vorhanden sein. Der Name darf nicht mehr als 256 Zeichen lang sein.<BR><br>Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt. Wenn Sie beispielsweise **contoso.com**eingeben, gibt die Suche auch die Domäne **IT.contoso.com**zurück.<BR><br>Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden. Skype for Business Server verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.
    
      - Wenn Sie den Zugriff auf Diese Verbunddomäne auf Benutzer eines bestimmten Servers einschränken möchten, auf dem der Access Edge-Dienst ausgeführt wird, geben Sie in **Access Edge Service (FQDN)** den FQDN des Servers der Verbunddomäne ein, auf dem der Access Edge-Dienst ausgeführt wird.    
      - Wenn Sie zusätzliche Informationen angeben möchten, geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.

6.  Klicken Sie auf **Commit ausführen**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jede Federated-Partner-Domäne, die Sie zulassen möchten.

Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für blockierte externe Domänen in Skype for Business Server 

Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche Domänen von der Föderation mit Ihrer Organisation blockiert werden. Die Liste der blockierten Domänen fungiert als Sperrliste (Auflistung expliziter Einträge, die nicht zulässig sind) und wird in der Föderationsdomänen Erkennung angewendet, wenn diese Option aktiviert ist. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Blockieren Sie eine oder mehrere externe Domänen, um eine Verbindung mit Ihrer Organisation herzustellen. Fügen Sie dazu die Domäne zur Liste der blockierten Domänen hinzu.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>So fügen Sie eine externe Domäne zur Liste der blockierten Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**.
4.  Klicken Sie auf **Verbunddomänen**, dann auf **neu**und dann auf **Blockierte Domäne**.
5.  Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:
    
      - Geben Sie in **Domänenname (oder FQDN)** den Namen der Partnerdomäne ein, die Sie blockieren möchten.

        > [!NOTE]  
        > Der Name darf nicht mehr als 256 Zeichen lang sein.<BR><br>Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt. Wenn Sie beispielsweise **contoso.com**eingeben, gibt die Suche auch die Domäne **IT.contoso.com**zurück.<BR><br>Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden. Skype for Business Server verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.
   
      - Optional Geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.

6.  Klicken Sie auf **Commit ausführen**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Föderationspartner, den Sie blockieren möchten.

Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Siehe auch

[Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Aktivieren oder Deaktivieren der Suche von Verbundpartnern](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

