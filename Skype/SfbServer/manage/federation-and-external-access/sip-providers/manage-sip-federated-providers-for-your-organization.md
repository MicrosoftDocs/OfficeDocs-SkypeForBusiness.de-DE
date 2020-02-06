---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: Hier erfahren Sie, wie Sie die Unterstützung für Benutzer von SIP-Verbund Anbietern konfigurieren.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818366"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Verwalten von SIP-Verbund Anbietern für Ihre Organisation in Skype for Business Server

Wenn Sie die Unterstützung für Benutzer von SIP-Verbund Anbietern konfigurieren möchten, müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren einer oder mehrerer externer Benutzerzugriffs Richtlinien zur Unterstützung der Kommunikation mit SIP-Föderations Dienstanbieter-Kontakten

  - Angeben, welche gehosteten Anbieter unterstützt werden sollen

  - Angeben, welche öffentlichen Chat Anbieter Sie unterstützen möchten

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in Skype for Business Server

Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Anbietern bereitgestellt werden.

Skype for Business Server verfügt über öffentliche Anbieter Konfigurationen für Chatnachrichten. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in der Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.

Als Standardeinstellung ist keiner der öffentlichen Anbieter aktiviert. Sie sollten den Lizenzvertrag und die Bereitstellungs Arbeit abschließen, bevor Sie die öffentlichen Anbieter aktivieren. Sie können den Anbieter aktivieren, bevor Sie die Lizenzierung und Bereitstellungs Arbeit abschließen. Die Benutzer können erst dann mit Kontakten an diesen Anbietern kommunizieren, wenn die Voraussetzungen für die Arbeit erfüllt sind. Einzelheiten zur Lizenzierung und Bereitstellung von öffentlichen Anbietern finden Sie unter [Konfigurieren von Richtlinien für den Zugriff durch öffentliche Benutzer](../external-access-policies/configure-policies-to-control-public-user-access.md).

Gehen Sie wie folgt vor, um öffentliche Anbieter zu erstellen oder zu bearbeiten.


### <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.

4.  Wenn Sie einen neuen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der öffentlichen Anbieter bearbeiten möchten, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:
    
      - **Aktivieren der Kommunikation mit diesem Anbieter**   Wenn Sie diese Einstellung auswählen, wird im mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Access Edge Service (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access-Edgedienst des Anbieters ein, den Sie konfigurieren. Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim öffentlichen Anbieter vornimmt.
    
      - **Standard Überprüfungsstufe:**   die Standardeinstellung, die es **Benutzern ermöglicht, mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        **Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen. Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des öffentlichen Anbieters kontaktieren kann.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern in Skype for Business Server

Mit der Instant Messaging-Konnektivität (im) des gehosteten Anbieters können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von gehosteten Anbietern bereitgestellt werden.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.

Gehen Sie wie folgt vor, um gehostete Anbieter zu erstellen oder zu bearbeiten.

### <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **gehosteter Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der gehosteten Anbieter bearbeiten möchten, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:
    
      - **Aktivieren der Kommunikation mit diesem Anbieter**   durch Auswählen dieser Einstellung wird die Kommunikation mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Access Edge Service (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access Edge-Diensts des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt werden und sollten nur geändert werden, wenn der gehostete Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim gehosteten Anbieter vornimmt.
    
      - **Standard Überprüfungsstufe:**   die Standardeinstellung, die es **Benutzern ermöglicht, mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        **Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen. Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.


## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien für den Zugriff durch öffentliche Benutzer](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

