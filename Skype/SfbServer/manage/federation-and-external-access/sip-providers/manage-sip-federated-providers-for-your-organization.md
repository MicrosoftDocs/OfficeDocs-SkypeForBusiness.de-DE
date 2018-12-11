---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informationen Sie zum Konfigurieren der Unterstützung für Benutzer von SIP-partnerverbundanbietern zu aktivieren.
ms.openlocfilehash: 111a71f95f3ae6a6c9dec90f5c0b29df07266fd2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222961"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Verwalten der Anbieter für Ihre Organisation in Skype für Business Server SIP-Verbund

Zum Konfigurieren der Unterstützung für Benutzer von SIP-partnerverbundanbietern zu aktivieren, müssen Sie folgende Aktionen ausführen:

  - Konfigurieren Sie eine oder mehrere externe Benutzer Zugriffsrichtlinien zur Unterstützung bei der Kommunikation mit SIP-partnerverbundanbieter-Kontakten

  - Geben Sie an welche gehosteten Anbieter Sie unterstützen möchten

  - Geben Sie die öffentlichen IM-Dienstanbieter, die Sie unterstützen möchten.

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von öffentlichen SIP-Verbund-Dienstanbieter in Skype für Business Server

Öffentliche instant messaging (IM)-Diensten kann Benutzer in Ihrer Organisation, per Sofortnachricht mit Benutzern von Instant Messaging-Dienste öffentliche Anbieter kommunizieren.

Skype für Business Server hat Sofortnachrichtendienst Konfigurationen für instant messaging. Jeden öffentlichen Anbieter wird mit der Anbieter Edge Server vollqualifizierten Domänennamen und die Überprüfung Standardstufe **durch Benutzer zulassen für die Kommunikation nur mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** konfiguriert.

Als Standard festlegen werden keine der öffentlichen Anbieter aktiviert. Schließen Sie die Lizenzvertrag sowie die Bereitstellung von Arbeit, bevor Sie öffentliche Anbieter aktivieren. Sie können den Anbieter aktivieren, vor dem Abschließen der Lizenzierung und Bereitstellung. Benutzer werden nicht kommunizieren mit Kontakten auf die Anbieter, bis die Untersuchung Arbeit abgeschlossen ist. Details zu Lizenzierung und Bereitstellung der öffentlichen Anbieter finden Sie unter [Configure Policies öffentliche Benutzer hinsichtlich steuern](../external-access-policies/configure-policies-to-control-public-user-access.md).

Verwenden Sie das folgende Verfahren zum Erstellen oder bearbeiten Sie öffentliche Anbieter.


### <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **SIP Federated Providers**.

4.  Wenn Sie einen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der Dienstanbieter bearbeiten müssen, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund-Dienstanbieter bearbeiten** können Sie eingeben oder bearbeiten die folgenden Einstellungen:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   Instant Messaging mit diesem Anbieter Benutzern ermöglicht diese Einstellung auswählen.
    
      - **Anbietername:**   eine erforderliche Eigenschaft; geben, die der Namen des Anbieters wie er in der Liste der SIP Federated Providers nachvollzogen werden.
    
      - **Zugriffs-edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-edgedienst des Anbieters, die Sie konfigurieren. Diese Informationen als ein Standardelement bereitgestellt wird und sollte nur geändert werden, wenn Sie der öffentliche Anbieter eine Änderung an den FQDN des Zugriffs-edgediensts an den öffentlichen Anbieter vornimmt.
    
      - **Default Überprüfungsstufen:**   die Standardeinstellung beschränken **Benutzern erlauben, kommunizieren mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** Kommunikation mit Kontakten, die Sie akzeptiert haben und in der Kontaktliste enthalten sind.
        
        Auswählen von **Benutzern erlauben, die für alle Benutzer mit diesem Anbieter kommunizieren** entfernt die Einschränkung, dass Sie empfangen und einen Kontakt einladen akzeptiert haben müssen. Diese Einstellung schränkt nicht, die Sie aus den öffentlichen Anbieter Netzwerk wenden können.

7.  Wenn Sie sind Konfigurieren der Einstellungen, klicken Sie auf **Commit** , zu speichern oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von gehosteten Anbietern von SIP-Verbund in Skype für Business Server

Gehostete Anbieter instant messaging (IM)-Konnektivität können Benutzer in Ihrer Organisation, um Sofortnachrichten zu verwenden, um die Kommunikation mit Benutzern von Instant Messaging-Diensten von gehosteten Anbietern bereitgestellt.

Jede gehosteten Anbieter wird mit der Anbieter Edge Server vollqualifizierten Domänennamen und die Überprüfung Standardstufe **durch Benutzer zulassen für die Kommunikation nur mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** konfiguriert.

Verwenden Sie das folgende Verfahren zum Erstellen oder bearbeiten Sie gehostete Anbieter.

### <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **SIP Federated Providers**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **gehosteter Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der gehosteten Anbieter bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund-Dienstanbieter bearbeiten** können Sie eingeben oder bearbeiten die folgenden Einstellungen:
    
      - **Kommunikation mit diesem Anbieter aktivieren**   ermöglicht die Kommunikation mit diesem Anbieter Benutzer diese Einstellung auswählen.
    
      - **Anbietername:**   eine erforderliche Eigenschaft; geben, die der Namen des Anbieters wie er in der Liste der SIP Federated Providers nachvollzogen werden.
    
      - **Zugriffs-edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-edgedienst der gehosteten Anbieter, den Sie konfigurieren. Diese Informationen vom gehosteten Anbieter bereitgestellt werden soll, und sollte nur geändert werden, wenn der gehostete Anbieter eine Änderung an den FQDN des Zugriffs-edgediensts auf den gehosteten Anbieter vornimmt.
    
      - **Default Überprüfungsstufen:**   die Standardeinstellung beschränken **Benutzern erlauben, kommunizieren mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** Kommunikation mit Kontakten, die Sie akzeptiert haben und in der Kontaktliste enthalten sind.
        
        Auswählen von **Benutzern erlauben, die für alle Benutzer mit diesem Anbieter kommunizieren** entfernt die Einschränkung, dass Sie empfangen und einen Kontakt einladen akzeptiert haben müssen. Diese Einstellung schränkt nicht, die Sie aus der gehosteten Anbieter Netzwerk wenden können.

7.  Wenn Sie sind Konfigurieren der Einstellungen, klicken Sie auf **Commit** , zu speichern oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.


## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzer hinsichtlich](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

