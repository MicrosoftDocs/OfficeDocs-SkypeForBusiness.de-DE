---
title: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Die Unterstützung für die Föderation ist erforderlich, damit Benutzer, die über ein Konto bei einem vertrauenswürdigen Kunden oder einer Partnerorganisation verfügen, einschließlich Partnerdomänen und Benutzer von öffentlichen Instant Messaging (im)-Anbieter Benutzern, die Sie unterstützen, die Zusammenarbeit mit Benutzern in Ihrem Organisation.
ms.openlocfilehash: 86cc3e66b2e3252b6b25ff4bef09d3abeb4badf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280243"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in Skype for Business Server

Die Unterstützung für die Föderation ist erforderlich, damit Benutzer, die über ein Konto bei einem vertrauenswürdigen Kunden oder einer Partnerorganisation verfügen, einschließlich Partnerdomänen und Benutzer von öffentlichen Instant Messaging (im)-Anbieter Benutzern, die Sie unterstützen, die Zusammenarbeit mit Benutzern in Ihrem Organisation. Föderation muss auch einen gehosteten Exchange-Dienstanbieter verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst wie Microsoft Exchange Online befinden. Wenn Sie eine Vertrauensstellung mit diesen externen Domänen eingerichtet haben, können Sie die Benutzer in diesen Domänen autorisieren, auf Ihre Bereitstellung zuzugreifen und an der Kommunikation zwischen Skype for Business Server teilzunehmen. Diese Vertrauensstellung wird als Föderation bezeichnet und ist nicht mit einer Active Directory-Vertrauensstellung verbunden oder abhängig davon.

Wenn Sie den Zugriff von Benutzern von Verbunddomänen unterstützen möchten, müssen Sie die Föderation aktivieren. Wenn Sie die Föderation für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:

  - **Aktivieren der Partnerdomänen Erkennung**   Wenn Sie diese Option aktivieren, verwendet Skype for Business Server DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu finden, die nicht in der Liste der zulässigen Domänen aufgelistet sind, und die eingehenden Datenverkehr automatisch auswerten. Föderationspartner und begrenzen oder Blockieren des Datenverkehrs basierend auf der Vertrauensebene, dem Umfang des Datenverkehrs und den Administratoreinstellungen. Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird. Details zum Steuern des Zugriffs durch Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Senden einer Verzichtserklärung zur Archivierung an Föderationspartner**     Haftungsausschluss Hinweis wird an verbundene Partner gesendet, die die Archivierung in Ihrer Bereitstellung durchgeführt haben. Wenn Sie die Archivierung externer Kommunikation mit Verbundpartner Domänen unterstützen, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten archiviert werden.

Wenn Sie den Zugriff von Benutzern von Verbunddomänen später vorübergehend oder dauerhaft verhindern möchten, können Sie den Verbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff auf den Verbundbenutzer für Ihre Organisation zu aktivieren oder zu deaktivieren, einschließlich der Angabe der entsprechenden Verbund Optionen, die für Ihre Organisation unterstützt werden sollen.

> [!NOTE]  
> Das Aktivieren des Föderations Unternehmens für Ihre Organisation gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, Routing in Verbunddomänen unterstützen Benutzer in Verbunddomänen können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung des Zugriffs von Verbundbenutzern konfiguriert haben. Benutzer von Anbietern öffentlicher Chat Dienste können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung öffentlicher Chats konfiguriert haben. Skype for Business Server kann keinen gehosteten Exchange-Dienst zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access (einschließlich Voicemail) oder automatischen Telefonzentralen Diensten für Benutzer verwenden, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine gehostete Sprache konfigurieren. e-Mail-Richtlinie, die Routinginformationen bereitstellt. Details zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden Sie unter [Verwalten von SIP-Verbunddomänen für Ihre Organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Wenn Sie die Kommunikation mit Benutzern von Chat Dienstanbietern unterstützen möchten, müssen Sie außerdem Richtlinien für deren Unterstützung konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten. Ausführliche Informationen finden Sie unter [Verwalten von SIP-Verbund Anbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Verbundbenutzer Zugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** , um den Zugriff durch den Verbundbenutzer für Ihre Organisation zu aktivieren.
    
      - Wenn Sie den Verbundbenutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .

6.  Wenn Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** aktiviert haben, gehen Sie folgendermaßen vor:
    
    1.  Wenn Sie die automatische Ermittlung von Partnerdomänen unterstützen möchten, aktivieren Sie das Kontrollkästchen **Discovery-Partnerdomänen Erkennung aktivieren** .
    
    2.  Wenn Ihre Organisation die Archivierung externer Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** .

7.  Klicken Sie auf **Commit ausführen**.

Damit Föderationsbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Verbundbenutzer Zugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md). Informationen zum Steuern des Zugriffs auf bestimmte Föderationsdomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen mithilfe von Windows PowerShell-Cmdlets

Verbund-und öffentliche Chat Verbindungen können auch mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>So aktivieren Sie Verbund-und öffentliche Chat Verbindungen

  - Um Verbund-und öffentliche Chat Verbindungen zu aktivieren, setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf true ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>So deaktivieren Sie die Verbindung zwischen Föderation und öffentlichen Chats

  - Zum Deaktivieren der Konnektivität für Verbund-und öffentliche Chats setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

