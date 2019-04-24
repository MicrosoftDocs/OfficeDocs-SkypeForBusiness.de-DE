---
title: Verwalten von SIP-Partnerdomänen für eine Organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Erfahren Sie, wie das Verwalten und Konfigurieren von SIP-Domänen, denen Sie einen Verbund mit konfigurieren können,
ms.openlocfilehash: 83623b41e0d9adb1e4539958344214fd2ebe0db9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199833"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Verwalten von Domänen für Ihre Organisation in Skype für Business Server SIP-Verbund


Zum Verwalten und Konfigurieren von SIP-Domänen, denen Sie einen Verbund mit konfigurieren können, können Sie Folgendes ein:

  - Erstellen Sie oder bearbeiten Sie eine Liste zulässiger Domänen Partnerdomänen SIP-Verbund.

  - Erstellen Sie oder bearbeiten Sie eine Liste blockierter Domänen der Domänen für SIP-Verbund.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für zulässige externe Domänen in Skype für Business Server

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche speziellen Domänen mit Ihrer Organisation eine Partnerschaft eingehen können. Konfigurieren Sie bestimmte externe Domänen als zulässigen Partnerdomänen. Fügen Sie hierzu jede Domäne zur Liste der zugelassenen Domänen. Auch wenn Partner-Ermittlung für Ihre Organisation aktiviert ist, wird dies ist die Domäne eines verbundpartners eingerichtet, das Kommunikation mit mehr als 1.000 Benutzer müssen möglicherweise oder senden müssen möglicherweise mehr als 20 Nachrichten pro Sekunde. Wenn Partner Discovery für Ihre Organisation nicht aktiviert ist, können nur Benutzer von externen Domänen, die Sie der Liste der zugelassenen Domänen hinzufügen Sofortnachrichten und Konferenzen mit Benutzern in Ihrer Organisation teilnehmen. Wenn Sie zum Einschränken des Zugriffs für eine verbunddomäne an einen bestimmten Server unter dem der Dienst Zugriffs-Edgeserver des verbundpartners möchten, können Sie den Domänennamen des Servers mit der Zugriffs-edgedienst für jede Domäne in der Liste der zugelassenen Domänen angeben.

> [!NOTE]  
> Dieses Verfahren beschreibt das Konfigurieren der Unterstützung für bestimmte Domänen, aber auch Implementierung der Unterstützung für Verbundbenutzer erfordert, dass Sie Unterstützung für Verbundbenutzer für Ihre Organisation zu aktivieren und konfigurieren und Anwenden von Richtlinien auf Steuerung, welche Benutzer können Zusammenarbeit mit Verbundbenutzer. Ausführliche Informationen zum Aktivieren der Unterstützung für Verbundbenutzer finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md). Ausführliche Informationen zum Konfigurieren von Richtlinien zur Steuerung der Verbund finden Sie unter [Konfigurieren von Richtlinien zur Steuerung federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>So fügen Sie eine externe Domäne zur Liste der zugelassenen Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Partnerdomänen**.
4.  Klicken Sie auf der Seite **Partnerdomänen** klicken Sie auf **neu**, und klicken Sie dann auf **zulässige Domäne**.
5.  **Neue Partnerdomänen**folgendermaßen Sie vor:
    
      - Geben Sie im **Domänenname (oder FQDN)** den Namen der verbundpartnerdomäne ein.       

        > [!NOTE]  
        > Dieser Name muss eindeutig sein und kann nicht als zulässige Domäne für diesen Server mit dem Zugriffs-Edgeservers-Dienst bereits vorhanden. Der Name darf die Länge von 256 Zeichen nicht überschreiten.<BR><br>Die Suche auf dem Domänennamen Verbundpartner führt eine Übereinstimmung Suffix. Beispielsweise wenn Sie **"contoso.com"** eingeben, wird die Suche auch die Domäne **it.contoso.com**zurückgeben.<BR><br>Eine verbundpartnerdomäne kann nicht gleichzeitig blockiert und zulässig. Skype für Business Server verhindert, dass dies geschieht, damit Sie keine synchronisieren Sie die Liste.
    
      - Geben Sie den FQDN des der Partnerdomäne Server Zugriffs-edgedienst ausgeführt, wenn zum Einschränken des Zugriffs für diese verbunddomäne für Benutzer von einem bestimmten Server in **Zugriffs-edgedienst (FQDN)** den Zugriffs-edgedienst ausgeführt werden soll.    
      - Wenn Sie zusätzliche Informationen bereitstellen möchten, geben Sie im Feld **Kommentar**Informationen, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.

6.  Klicken Sie auf **Commit ausführen**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jede verbundpartnerdomäne, die Sie zulassen möchten.

Um Verbundbenutzer Zugriff zu ermöglichen, müssen Sie auch die Unterstützung des Zugriffs durch Partnerbenutzer in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie konfigurieren und anwenden die Richtlinie auf Benutzer, die für die Zusammenarbeit mit Verbundbenutzer enthalten sein sollen. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Konfigurieren der Unterstützung für blockierte externe Domänen in Skype für Business Server 

Wenn Sie Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche Domänen mit Ihrer Organisation eine Föderation blockiert werden. Die Liste der blockierten Domänen fungiert als einer Sperrliste (Auflistung der expliziten Einträge, die nicht zulässig) und gelten in partnerverbunddomänen, wenn Sie diese Option aktiviert haben. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Blockieren Sie einen oder mehrere externe Domänen aus eine Verbindung mit Ihrer Organisation. Zu diesem Zweck fügen Sie die Domäne der Liste blockierter Domänen hinzu.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>So fügen Sie eine externe Domäne zur Liste der blockierten Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**.
4.  Klicken Sie auf **Partnerdomänen**, klicken Sie auf **neu**, und klicken Sie dann auf **Blockierte Domäne**.
5.  **Neue Partnerdomänen**folgendermaßen Sie vor:
    
      - Geben Sie im **Domänenname (oder FQDN)** den Namen der verbundpartnerdomäne, die Sie blockieren möchten.

        > [!NOTE]  
        > Der Name darf die Länge von 256 Zeichen nicht überschreiten.<BR><br>Die Suche auf dem Domänennamen Verbundpartner führt eine Übereinstimmung Suffix. Beispielsweise wenn Sie **"contoso.com"** eingeben, wird die Suche auch die Domäne **it.contoso.com**zurückgeben.<BR><br>Eine verbundpartnerdomäne kann nicht gleichzeitig blockiert und zulässig. Skype für Business Server verhindert, dass dies geschieht, damit Sie keine synchronisieren Sie die Liste.
   
      - (Optional) Geben Sie im Feld **Kommentar**Informationen, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.

6.  Klicken Sie auf **Commit ausführen**.
7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Verbundpartner, den Sie blockieren möchten.

Um Verbundbenutzer Zugriff zu ermöglichen, müssen Sie auch die Unterstützung des Zugriffs durch Partnerbenutzer in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie konfigurieren und anwenden die Richtlinie auf Benutzer, die für die Zusammenarbeit mit Verbundbenutzer enthalten sein sollen. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Siehe auch

[Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Aktivieren oder Deaktivieren der Suche von Verbundpartnern](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

