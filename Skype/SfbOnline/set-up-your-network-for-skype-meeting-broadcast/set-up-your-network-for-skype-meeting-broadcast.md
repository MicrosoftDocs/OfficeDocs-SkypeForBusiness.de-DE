---
title: Einrichten Ihres Netzwerks für Skype-Livekonferenz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Erfahren Sie mehr über die Skype-Live Konferenz-Funktion von Skype for Business Online, mit der Sie Besprechungen oder Ereignisse für große Online-Zielgruppen bis zu 10.000 Teilnehmer planen, erstellen und übertragen können.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990980"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Einrichten Ihres Netzwerks für Skype-Livekonferenz

Nach der [Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md) Skype-Livekonferenz müssen Sie Ihr Netzwerk konfigurieren. Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.

Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.

Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, das Sie zu Konferenzen einladen können, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.

## <a name="step-1-set-up-allowed-domains"></a>Schritt 1: Einrichten von zulässigen Domänen

Verwenden Sie **eine** der folgenden Methoden, um zulässige Domänen einzurichten:

## #

 **Methode 1: Verwenden des Admin Centers**

1. Wechseln Sie zum Admin Center, und klicken Sie dann im linken Navigationsbereich auf **Einstellungen** > **Services &amp; -Add-ins**, und wählen Sie dann **Skype for Business**aus.

2. Wählen Sie auf der Seite **externe Freigabe** unter **Domänen Ausnahmen**die Option **alle Domänen werden blockiert mit Ausnahme**aus, und geben Sie die folgenden Domänen ein, die durch ein Komma (,) getrennt sind:

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Klicken Sie auf **Speichern**.

## #

 **Methode 2: Verwenden von Windows PowerShell**

- Klicken Sie im **Startmenü**mit der rechten Maustaste auf **Windows PowerShell** , und klicken Sie dann auf **als Administrator ausführen**. Geben Sie im **Windows PowerShell** -Fenster jede Zeile ein, und drücken Sie die EINGABETASTE.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Schritt 2: Hinzufügen von Skype-Live Konferenz-Domänen,-URLs und-IP-Adressen

Im zweiten Schritt des Setupvorgangs fügen Sie zuerst die benötigten Domänen hinzu. Anschließend fügen Sie die IP-Adressen und URLs hinzu, die erforderlich sind, damit Skype-Livekonferenz funktioniert.

- **Fügen Sie die erforderlichen Skype for Business Online-Endpunkt-URLs und IP-Adressen hinzu, indem Sie sehen, welche hier erforderlich sind** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Einrichten von Skype-Livekonferenz in Hybridbereitstellungen und -organisationen

Wenn Sie über eine Skype for Business Online-Organisation und eine lokale Bereitstellung von lync Server 2010, Microsoft lync Server 2013 und Skype for Business Server 2015 verfügen und Benutzer sowohl online als auch lokal sind, gibt es weitere Einrichtungsschritte, die Sie ausführen müssen. Zusätzlich zu den oben genannten, um Ihre lokale Organisation für die Kommunikation mit Skype for Business Online zu aktivieren und allen Ihren Benutzern die Teilnahme an einer Skype-Live Konferenz zu ermöglichen. Die entsprechenden Anforderungen finden Sie unter [Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Verwandte Themen

[Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md)

[URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



