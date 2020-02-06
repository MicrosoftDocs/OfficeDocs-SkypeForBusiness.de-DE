---
title: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob Remotebenutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können. Wenn Sie den Zugriff durch Remotebenutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren.
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818296"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server

Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob Remotebenutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können. Wenn Sie den Zugriff durch Remotebenutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren. Website Richtlinien überschreiben die globale Richtlinie, und Benutzerrichtlinien überschreiben Website-und globale Richtlinien. Details zu den Richtlinientypen, die Sie konfigurieren können, finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md). Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

> [!NOTE]  
> Sie können Richtlinien konfigurieren, um den Remotebenutzerzugriff zu steuern, auch wenn Sie den Remotebenutzerzugriff für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Remotebenutzerzugriff für Ihre Organisation aktiviert ist. Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Remotebenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Details zum Angeben von Benutzern, die sich bei Skype for Business Server von Remotestandorten aus anmelden können, finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer](assign-an-external-user-access-policy.md).

Gehen Sie wie folgt vor, um jede Richtlinie für den externen Zugriff zu konfigurieren, die Sie zum Steuern des Remotebenutzerzugriffs verwenden möchten.


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie eine Richtlinie nur für die Kommunikation mit Remotebenutzern konfigurieren, aber jede Richtlinie, die Sie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, kann auch den Zugriff durch den Verbundbenutzer und den Zugriff auf öffentliche Benutzer konfigurieren. Details zum Konfigurieren von Richtlinien für die Unterstützung von Verbundbenutzern finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in Skype for Business Server](configure-policies-to-control-federated-user-access.md). Details zum Konfigurieren von Richtlinien für die Unterstützung öffentlicher Benutzer finden Sie unter [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Remotebenutzerzugriffs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:
    
      - Wenn Sie die globale Richtlinie für die Unterstützung des Remotebenutzerzugriffs konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableRemoteUsers** für eine Benutzerrichtlinie, die die Kommunikation für Remotebenutzer aktiviert).
    
      - Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Wenn Sie den Zugriff durch Remotebenutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Zugriff durch Remotebenutzer in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die eine Remoteverbindung herstellen können sollen. Ausführliche Informationen finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer](assign-an-external-user-access-policy.md).
