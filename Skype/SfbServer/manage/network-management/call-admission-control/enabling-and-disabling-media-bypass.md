---
title: Aktivieren und Deaktivieren der Medienumgehung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel, um die Medienumgehung mithilfe der Skype for Business Server Systemsteuerung zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: ffad0889d048bf1bd806b5211c42af1c9224e2451ebb6a25633c31f378d23499
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313053"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Aktivieren und Deaktivieren der Medienumgehung in Skype for Business Server

Verwenden Sie die Verfahren in diesem Artikel, um die Medienumgehung mithilfe der Skype for Business Server Systemsteuerung zu aktivieren oder zu deaktivieren.

## <a name="enable-network-media-bypass"></a>Aktivieren der Netzwerkmedienumgehung 

Medienumgehungseinstellungen gelten global für eine Skype for Business Server Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Ausführliche Informationen dazu, wann die Medienumgehung verwendet werden soll, finden Sie unter ["Planen der Medienumgehung".](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Sie können die Medienumgehung über die Skype for Business Server Systemsteuerung aktivieren und konfigurieren.


### <a name="to-enable-and-configure-media-bypass"></a>So aktivieren und konfigurieren Sie die Medienumgehung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Global".**

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** auf das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   Wählen Sie diese Option aus, um eine Medienumgehung für alle Anrufe anzustreben. Diese Option ist nicht verfügbar, wenn die Anrufsteuerung aktiviert ist. Ist die Anrufsteuerung nicht aktiviert, wählen Sie diese Option in den folgenden Situationen:
        
          - Es besteht keine Notwendigkeit zur Bandbreitensteuerung.
        
          - Es ist keine fein abgestimmte Konfiguration erforderlich, mit der die Anforderung einer Medienumgehung erkannt wird.
        
          - Zwischen Gateways und Clients ist vollständige Konnektivität gegeben.
    
      - **Konfiguration von Standorten und Regionen verwenden**   Wenn die Anrufsteuerung aktiviert wurde, ist diese Option standardmäßig aktiviert und kann nicht geändert werden. Ist diese Option ausgewählt, wird anhand der Standorte und Regionen in der Netzwerkkonfiguration ermittelt, ob eine Medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie eine Umgehung für Standorte aktivieren, die nicht zugeordnet sind. Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die mit einer bestimmten Region verknüpft sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die mit derselben Region verknüpft sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die mit den Zweigstandorten verknüpften Subnetze angeben, statt sämtliche, mit allen Standorten verknüpfte Subnetze angeben zu müssen. Es wird empfohlen, das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte** nicht zu aktivieren, wenn die Anrufsteuerung aktiviert ist.

8.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.


## <a name="disable-network-media-bypass"></a>Deaktivieren der Netzwerkmedienumgehung

Medienumgehungseinstellungen gelten global für eine Skype for Business Server Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Ausführliche Informationen dazu, wann die Medienumgehung verwendet werden soll, finden Sie unter ["Planen der Medienumgehung".](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) Sie können die Medienumgehung über die Skype for Business Server Systemsteuerung deaktivieren. 


### <a name="to-disable-media-bypass"></a>So deaktivieren Sie die Medienumgehung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Global".**

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Deaktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.

  
