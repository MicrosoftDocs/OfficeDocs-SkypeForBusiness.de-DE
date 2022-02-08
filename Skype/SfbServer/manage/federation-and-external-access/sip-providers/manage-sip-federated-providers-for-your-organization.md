---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Erfahren Sie, wie Sie die Unterstützung für Benutzer von SIP-Partnerverbundanbietern konfigurieren.
ms.openlocfilehash: b6a28714ec3ad81470f362f49605d0be4805dbe2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392557"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Verwalten von SIP-Partnerverbundanbietern für Ihre Organisation in Skype for Business Server

Um die Unterstützung für Benutzer von SIP-Verbundanbietern zu konfigurieren, müssen Sie folgendermaßen vorgehen:

  - Konfigurieren einer oder mehrerer Richtlinien für den Externen Benutzerzugriff zur Unterstützung der Kommunikation mit Kontakten mit SIP-Partnerverbundanbietern

  - Geben Sie an, welche gehosteten Anbieter Unterstützt werden sollen

  - Angeben der öffentlichen Chatanbieter, die Sie unterstützen möchten

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten öffentlicher SIP-Partnerverbundanbieter in Skype for Business Server

Die Konnektivität mit öffentlichen Chatnachrichten ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chatnachrichten, um mit Benutzern von Chatdiensten zu kommunizieren, die von öffentlichen Anbietern bereitgestellt werden.

Skype for Business Server verfügt über Konfigurationen öffentlicher Anbieter für Chatnachrichten. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers für den jeweiligen Anbieter sowie mit der Standardüberprüfungsstufe **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** konfiguriert.

In der Standardeinstellung ist kein öffentlicher Anbieter aktiviert. Bevor Sie die öffentlichen Anbieter aktivieren, sollten Sie zunächst die Lizenzvereinbarung und die Bereitstellungsmaßnahmen abschließen. Es ist möglich, die Anbieter vor Abschluss der Lizenzvereinbarung und der Bereitstellungsmaßnahmen zu aktivieren. Benutzer können jedoch nicht mit Kontakten dieser Anbieter kommunizieren, bevor die Vorbereitungsmaßnahmen nicht abgeschlossen sind. Ausführliche Informationen zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des öffentlichen Benutzerzugriffs"](../external-access-policies/configure-policies-to-control-public-user-access.md).

Verwenden Sie das folgende Verfahren, um öffentliche Anbieter zu erstellen oder zu bearbeiten.


### <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter**.

4.  Wenn Sie einen öffentlichen Anbieter erstellen möchten, klicken Sie auf **Neu** und dann auf **Öffentlicher Anbieter**.

5.  Um einen Eintrag aus der Liste der öffentlichen Anbieter zu bearbeiten, wählen Sie einen öffentlichen Anbieter aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   Wenn Sie diese Einstellung auswählen, wird die Sofortnachrichtenfunktion für Benutzer dieses Anbieters aktiviert.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**    Erforderliche Eigenschaft. Geben Sie den vollqualifizierten Domänennamen für den Zugriffs-Edgedienst des Anbieters ein, den Sie konfigurieren möchten. Diese Informationen werden standardmäßig bereitgestellt. Sie sollten nur geändert werden, wenn beim öffentlichen Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts vorgenommen wird.
    
      - **Standardüberprüfungsstufe:**    Mit der Standardeinstellung **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** wird die Kommunikation auf Kontakte beschränkt, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Durch Auswählen von **Benutzer können mit allen Benutzern mit diesem Anbieter kommunizieren** wird die Einschränkung entfernt, dass eine Kontakteinladung empfangen und angenommen worden sein muss. Diese Einschränkung hat keine Auswirkungen darauf, welche Benutzer aus dem Netzwerk des öffentlichen Anbieters mit Ihnen Kontakt aufnehmen können.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit**, um die Änderungen zu speichern, oder auf **Abbrechen**, um die Änderungen zu verwerfen.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten gehosteter SIP-Verbundanbieter in Skype for Business Server

Die Chatkonnektivität eines gehosteten Anbieters ermöglicht Es Benutzern in Ihrer Organisation, Chatnachrichten zu verwenden, um mit Benutzern von Chatdiensten zu kommunizieren, die von gehosteten Anbietern bereitgestellt werden.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers des Anbieters sowie der Standardüberprüfungsstufe **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** konfiguriert.

Verwenden Sie das folgende Verfahren, um gehostete Anbieter zu erstellen oder zu bearbeiten.

### <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partnerverbundanbieter**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **Neu** und anschließend auf **Gehosteter Anbieter**.

5.  Wenn Sie in der Liste der gehosteten Anbieter einen Eintrag bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partnerverbundanbieter bearbeiten** können Sie folgende Einstellungen eingeben oder bearbeiten:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   Die Auswahl dieser Einstellung ermöglicht die Kommunikation mit den Benutzen dieses Anbieters.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**    Erforderliche Eigenschaft; geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienstes des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt und nur dann geändert werden, wenn der gehostete Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim gehosteten Anbieter vornimmt.
    
      - **Standardüberprüfungsstufe:**    Die Standardeinstellung **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Die Auswahl der Option **Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet** entfernt die Einschränkung, dass Sie eine Kontaktanfrage erhalten und angenommen haben müssen. Diese Einstellung hat keine Auswirkungen darauf, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Einstellungen konfiguriert haben, klicken Sie auf **Commit**, um zu speichern oder auf **Abbrechen**, um die Änderungen zu verwerfen.


## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zum Steuern der öffentlichen Benutzerzurückrufe](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

