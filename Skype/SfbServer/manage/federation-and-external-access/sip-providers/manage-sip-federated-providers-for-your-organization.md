---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: Informationen zum Konfigurieren der Unterstützung für Benutzer von SIP-Verbundanbietern.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823565"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Verwalten von SIP-Verbundanbietern für Ihre Organisation in Skype for Business Server

Gehen Sie wie folgt vor, um die Unterstützung für Benutzer von SIP-Verbundanbietern zu konfigurieren:

  - Konfigurieren einer oder mehrere Richtlinien für den externen Benutzerzugriff zur Unterstützung der Kommunikation mit Kontakten des SIP-Verbundanbieters

  - Angeben, welche gehosteten Anbieter unterstützt werden sollen

  - Geben Sie an, welche öffentlichen Anbieter von Internetdiensten unterstützt werden sollen.

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von öffentlichen SIP-Verbundanbietern in Skype for Business Server

Die Verbindung mit öffentlichen Sofortnachrichtendiensten ermöglicht Benutzern in Ihrer Organisation die Verwendung von Sofortnachrichten für die Kommunikation mit Benutzern von Chatdiensten, die von öffentlichen Anbietern bereitgestellt werden.

Skype for Business Server verfügt über Konfigurationen öffentlicher Anbieter für Chatnachrichten. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers für den jeweiligen Anbieter sowie mit der Standardüberprüfungsstufe **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** konfiguriert.

In der Standardeinstellung ist kein öffentlicher Anbieter aktiviert. Bevor Sie die öffentlichen Anbieter aktivieren, sollten Sie zunächst die Lizenzvereinbarung und die Bereitstellungsmaßnahmen abschließen. Es ist möglich, die Anbieter vor Abschluss der Lizenzvereinbarung und der Bereitstellungsmaßnahmen zu aktivieren. Benutzer können jedoch nicht mit Kontakten dieser Anbieter kommunizieren, bevor die Vorbereitungsmaßnahmen nicht abgeschlossen sind. Weitere Informationen zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter "Konfigurieren von Richtlinien zum [Steuern der öffentlichen Benutzerfreundlichkeit".](../external-access-policies/configure-policies-to-control-public-user-access.md)

Verwenden Sie das folgende Verfahren, um öffentliche Anbieter zu erstellen oder zu bearbeiten.


### <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter**.

4.  Wenn Sie einen öffentlichen Anbieter erstellen möchten, klicken Sie auf **Neu** und dann auf **Öffentlicher Anbieter**.

5.  Um einen Eintrag aus der Liste der öffentlichen Anbieter zu bearbeiten, wählen Sie einen öffentlichen Anbieter aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   Wenn Sie diese Einstellung auswählen, wird die Sofortnachrichtenfunktion für Benutzer dieses Anbieters aktiviert.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**   Eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgediensts des Anbieters ein, den Sie konfigurieren. Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim öffentlichen Anbieter vor nimmt.
    
      - **Standardüberprüfungsstufe:**    Mit der Standardeinstellung **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** wird die Kommunikation auf Kontakte beschränkt, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Durch Auswählen von **Benutzer können mit allen Benutzern mit diesem Anbieter kommunizieren** wird die Einschränkung entfernt, dass eine Kontakteinladung empfangen und angenommen worden sein muss. Diese Einschränkung hat keine Auswirkungen darauf, welche Benutzer aus dem Netzwerk des öffentlichen Anbieters mit Ihnen Kontakt aufnehmen können.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit**, um die Änderungen zu speichern, oder auf **Abbrechen**, um die Änderungen zu verwerfen.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Skype for Business Server

Die Konnektivität für Instant Messaging (Instant Messaging) eines gehosteten Anbieters ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chatnachrichten für die Kommunikation mit Benutzern von Chatdiensten, die von gehosteten Anbietern bereitgestellt werden.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers des Anbieters sowie der Standardüberprüfungsstufe **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** konfiguriert.

Verwenden Sie das folgende Verfahren, um gehostete Anbieter zu erstellen oder zu bearbeiten.

### <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partnerverbundanbieter**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **Neu** und anschließend auf **Gehosteter Anbieter**.

5.  Wenn Sie in der Liste der gehosteten Anbieter einen Eintrag bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partnerverbundanbieter bearbeiten** können Sie folgende Einstellungen eingeben oder bearbeiten:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   Die Auswahl dieser Einstellung ermöglicht die Kommunikation mit den Benutzen dieses Anbieters.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**   Eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgediensts des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt und nur dann geändert werden, wenn der gehostete Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim gehosteten Anbieter vornimmt.
    
      - **Standardüberprüfungsstufe:**    Die Standardeinstellung **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Die Auswahl der Option **Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet** entfernt die Einschränkung, dass Sie eine Kontaktanfrage erhalten und angenommen haben müssen. Diese Einstellung hat keine Auswirkungen darauf, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Einstellungen konfiguriert haben, klicken Sie auf **Commit**, um zu speichern oder auf **Abbrechen**, um die Änderungen zu verwerfen.


## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zum Steuern der öffentlichen Benutzerfreundlichkeit](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

