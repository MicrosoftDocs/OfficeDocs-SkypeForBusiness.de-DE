---
title: Aktivieren und Deaktivieren der medienumgehung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Führen Sie die in diesem Artikel beschriebenen Verfahren aus, um die medienumgehung mithilfe des Skype for Business Server-Control Panels zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817544"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Aktivieren und Deaktivieren der Medienumgehung in Skype for Business Server

Führen Sie die in diesem Artikel beschriebenen Verfahren aus, um die medienumgehung mithilfe des Skype for Business Server-Control Panels zu aktivieren oder zu deaktivieren.

## <a name="enable-network-media-bypass"></a>Aktivieren der Netzwerkmedien Umgehung 

Medienumgehungseinstellungen gelten global für eine Skype for Business Server-Bereitstellung. Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen. Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Sie können die medienumgehung über das Skype Control Panel für Unternehmens-Server aktivieren und konfigurieren.


### <a name="to-enable-and-configure-media-bypass"></a>So aktivieren und konfigurieren Sie die medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration. Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Klicken Sie auf der Seite **globale Einstellungen bearbeiten** auf das Kontrollkästchen **medienumgehung aktivieren** .

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   wählen Sie diese Option aus, um bei allen Anrufen medienumgehung zu versuchen. Diese Option steht nicht zur Verfügung, wenn die Anrufsteuerung (Call Admission Control, CAC) aktiviert ist. Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Fällen aus:
        
          - Die Bandbreitensteuerung ist nicht erforderlich.
        
          - Es besteht keine Notwendigkeit für eine fein abgestimmte Konfiguration, um festzustellen, wann eine Umgehung erfolgen soll.
        
          - Es besteht eine vollständige Konnektivität zwischen Gateways und Clients.
    
      - **Verwenden von Websites und der Regions Konfiguration**   wenn CAC aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden. Wenn diese Option ausgewählt ist, werden Netzwerk Konfigurations Websites und-Regionen verwendet, um zu ermitteln, wann eine medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie die Umgehung für Websites aktivieren, die nicht zugeordnet sind. Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Websites aktivieren** nur, wenn Sie über eine oder mehrere große Websites verfügen, die dem gleichen Bereich zugeordnet sind, die keine Bandbreiteneinschränkungen aufweisen (beispielsweise eine große zentrale Website), und Sie verfügen auch über einige Verzweigungs Websites, die dem gleichen Bereich zugeordnet sind, für den es keine Bandbreiteneinschränkungen gibt. Wenn Sie die Umgehung für nicht zugeordnete Websites aktivieren, wird die Konfiguration optimiert, da Sie nur die Subnetze angeben, die den Zweigstellen zugeordnet sind, anstatt alle Subnetze anzugeben, die allen Websites zugeordnet sind. Wir empfehlen, dass Sie das Kontrollkästchen **Bypass für nicht zugeordnete Websites aktivieren** nicht aktivieren, wenn CAC aktiviert ist.

8.  Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.


## <a name="disable-network-media-bypass"></a>Deaktivieren der Netzwerkmedien Umgehung

Medienumgehungseinstellungen gelten global für eine Skype for Business Server-Bereitstellung. Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen. Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Sie können die medienumgehung über das Skype Control Panel für Unternehmen-Server deaktivieren. 


### <a name="to-disable-media-bypass"></a>So deaktivieren Sie die medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration. Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Deaktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .

7.  Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.

  
