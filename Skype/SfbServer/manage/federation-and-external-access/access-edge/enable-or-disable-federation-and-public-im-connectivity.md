---
title: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: Die Unterstützung für einen Partnerverbund ist erforderlich, um Benutzern mit einem Konto in einer vertrauenswürdigen Kunden- oder Partnerorganisation – Partnerdomänen und Benutzer eines unterstützten öffentlichen Sofortnachrichtenanbieters eingeschlossen – die Zusammenarbeit mit Benutzern in Ihrer Organisation zu ermöglichen.
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675747"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität in Skype for Business Server

Die Unterstützung für einen Partnerverbund ist erforderlich, um Benutzern mit einem Konto in einer vertrauenswürdigen Kunden- oder Partnerorganisation – Partnerdomänen und Benutzer eines unterstützten öffentlichen Sofortnachrichtenanbieters eingeschlossen – die Zusammenarbeit mit Benutzern in Ihrer Organisation zu ermöglichen. Der Partnerverbund ist auch erforderlich, um einen gehosteten Exchange-Dienstanbieter zu verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, z. B. Microsoft Exchange Online. Wenn Sie eine Vertrauensstellung mit diesen externen Domänen eingerichtet haben, können Sie Benutzer in diesen Domänen autorisieren, auf Ihre Bereitstellung zuzugreifen und an Skype for Business Server Kommunikation teilzunehmen. Diese Vertrauensstellung wird Partnerverbund genannt, und es besteht weder ein Zusammenhang mit noch eine Abhängigkeit von einer Active Directory-Vertrauensstellung.

Zur Unterstützung des Benutzerzugriffs auf Partnerdomänen müssen Sie den Partnerverbund aktivieren. Wenn Sie den Partnerverbund für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:

  - **Aktivieren der Partnerdomänenermittlung**   Wenn Sie diese Option aktivieren, versucht Skype for Business Server mithilfe von DNS-Einträgen (Domain Name System) Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, wobei eingehender Datenverkehr von ermittelten Verbundpartnern automatisch ausgewertet und der Datenverkehr basierend auf der Vertrauensstufe, dem Umfang des Datenverkehrs und den Administratoreinstellungen eingeschränkt oder blockiert wird. Wenn Sie diese Option nicht auswählen, ist der Partnerbenutzerzugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste der zulässigen Domänen einschließen. Unabhängig davon, ob Sie diese Option auswählen oder nicht, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen der Access Edge-Dienst in der Verbunddomäne ausgeführt wird. Ausführliche Informationen zum Steuern des Zugriffs durch Verbunddomänen finden [Sie unter Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Senden Sie einen Archivierungshaftungsausschluss an Verbundpartner**   Dieser Haftungsausschluss wird an Verbundpartner gesendet, um sie darüber zu informieren, dass die Archivierung innerhalb der Bereitstellung ausgeführt wurde. Wenn Sie die Archivierung der externen Kommunikation mit Verbundpartnerdomänen unterstützen, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten in Kenntnis zu setzen.

Wenn Sie den Zugriff durch Benutzer von Partnerdomänen zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie den Partnerverbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Partnerbenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren und um die geeigneten Partnerverbundoptionen festzulegen, die für Ihre Organisation unterstützt werden sollen.

> [!NOTE]  
> Durch aktivieren des Partnerverbunds für Ihre Organisation wird nur angegeben, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, das Routing an Verbunddomänen unterstützen. Benutzer in Verbunddomänen können nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie konfigurieren, um den Zugriff auf Verbundbenutzer zu unterstützen. Benutzer von öffentlichen Chatdienstanbietern können nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie konfigurieren, um die Konnektivität öffentlicher Chatnachrichten zu unterstützen. Skype for Business Server können einen gehosteten Exchange-Dienst nicht verwenden, um Anrufbeantwortung, Outlook Voice Access (einschließlich Voicemail) oder automatische Telefonzentralendienste für Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine richtlinie für gehostete Voicemail konfigurieren, die Routing bereitstellt. Informationen. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden [Sie unter Verwalten von SIP-Verbunddomänen für Ihre Organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Wenn Sie die Kommunikation mit Benutzern von Chatdienstanbietern unterstützen möchten, müssen Sie außerdem Richtlinien für die Unterstützung konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten. Ausführliche Informationen finden   [Sie unter Verwalten von SIP-Verbundanbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Partnerbenutzerzugriff für Ihre Organisation

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei jedem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren**, um den Zugriff durch Remotebenutzer für Ihre Organisation zuzulassen.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Partnerbenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Führen Sie nach Aktivierung des Kontrollkästchens **Kommunikation mit Partnerbenutzern aktivieren** eine der folgenden Aktionen aus:
    
    1.  Aktivieren Sie das Kontrollkästchen **Suche von Partnerdomänen aktivieren**, um die automatische Suche von Partnerdomänen zu unterstützen.
    
    2.  Wenn Ihre Organisation die Archivierung der externen Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**.

7.  Klicken Sie auf **Commit**.

Um Verbundbenutzern die Zusammenarbeit mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zu ermöglichen, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Partnerbenutzerzugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md). Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden [Sie unter Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität mithilfe Windows PowerShell Cmdlets

Verbund- und öffentliche Chatverbindungen können auch mithilfe von Windows PowerShell und dem cmdlet Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>So aktivieren Sie partnerverbund- und öffentliche Chatkonnektivität

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "True" ($True) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu aktivieren:<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>So deaktivieren Sie die Verbund- und öffentliche Chatkonnektivität

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "False" ($False) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu deaktivieren:<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

