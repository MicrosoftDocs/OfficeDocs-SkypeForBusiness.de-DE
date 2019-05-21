---
title: 'Lync Server 2013: Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie aktivieren und konfigurieren den Zugriff durch externe Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280103"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server

Die Bereitstellungeines Edgeserver oder eines Edge-Pools ist der erste Schritt zur Unterstützung externer Benutzer. Details zum Bereitstellen von Edgeserver finden Sie unter [Bereitstellen von Edgeserver in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Nach der Installation und Konfiguration Ihrer internen Bereitstellung von Skype for Business Server können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die über SIP-Konten in Ihren Active Directory-Domänendiensten (AD DS) verfügen. Die Zusammenarbeit kann das Senden und empfangen von Sofortnachrichten sowie die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch bekannt als "Besprechungen") umfassen. Sie aktivieren und konfigurieren den Zugriff durch externe Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können. Externe Benutzer können Remotebenutzer Ihrer Bereitstellung, Verbundbenutzer (einschließlich unterstützter Benutzer von öffentlichen Instant Messaging (im)-Dienstanbietern) und anonyme Teilnehmer an Konferenzen einbeziehen.

Wenn Ihre Bereitstellung die Installation eines Skype for Business Server-Edge-Servers oder eines Edge-Pools enthielt, wird der Umfang möglicher Kommunikationstypen stark erweitert, und es werden eine Reihe von Optionen für den Zugriff durch externe Benutzer, die Kommunikation mit Mitgliedern anderer SIP-Verbund Domänen und SIP-Verbund Anbieter. Nachdem Sie den Edgeserver oder den Edge-Pool eingerichtet haben, aktivieren Sie die Typen des Zugriffs auf externe Benutzer, die Sie bereitstellen möchten, und konfigurieren die Richtlinien für die Steuerung für den externen Zugriff. In Skype for Business Server aktivieren und konfigurieren Sie den Zugriff und die Richtlinien für externe Benutzer über das Skype for Business Server Control Panel, die [Skype for Business Server-Verwaltungsshell](../management-shell.md)oder beides, basierend auf den Aufgabenanforderungen. 



> [!IMPORTANT]  
> Wenn Sie Ihre Konfiguration und Richtlinien für den Zugriff durch externe Benutzer entwerfen, müssen Sie die Rangfolge der Richtlinien und die Anwendung der Richtlinien kennen. Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


Standardmäßig sind keine Richtlinien für die Unterstützung des Zugriffs externer Benutzer konfiguriert, einschließlich des Remotebenutzerzugriffs, des Zugriffs auf den Verbundbenutzer, auch wenn Sie die Unterstützung für den externen Benutzer Zugriff für Ihre Organisation bereits aktiviert haben. Um die Verwendung des Zugriffs auf externe Benutzer zu steuern, müssen Sie eine oder mehrere Richtlinien konfigurieren und den Typ des für jede Richtlinie unterstützten externen Benutzerzugriffs angeben. Dazu gehören die folgenden Richtlinien für den externen Zugriff:

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind keine Optionen für den externen Benutzer Zugriff in der globalen Richtlinie aktiviert. Zur Unterstützung des Zugriffs externer Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützt werden. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, aber Website Richtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, werden Sie nicht entfernt. Stattdessen setzen Sie Sie auf die Standardeinstellung zurück.

  - **Website Richtlinie**   Sie können eine oder mehrere Website Richtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff externer Benutzer auf bestimmte Websites zu begrenzen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, geben Sie möglicherweise eine Website Richtlinie an, die den Remotebenutzerzugriff für eine bestimmte Website deaktiviert. Standardmäßig wird eine Website Richtlinie auf alle Benutzer dieser Website angewendet, aber Sie können einem Benutzer eine Benutzerrichtlinie zuweisen, um die Website Richtlinieneinstellung zu überschreiben.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer zu begrenzen. Die Konfiguration in der Benutzerrichtlinie überschreibt die globale und die Website Richtlinie, jedoch nur für bestimmte Benutzer, denen die Benutzerrichtlinie zugewiesen ist. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und der Website Richtlinie aktivieren, geben Sie möglicherweise eine Benutzerrichtlinie an, die den Zugriff durch Remotebenutzer deaktiviert und diese Benutzerrichtlinie dann bestimmten Benutzern zuweist. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie Sie auf einen oder mehrere Benutzer anwenden, bevor Sie wirksam wird.

Wenn Sie feststellen möchten, welche Konfigurationseinstellungen und welche Richtlinien Sie erstellen oder bearbeiten müssen, lesen Sie die folgenden Entscheidungspunkte:

**Möchten Sie zulassen, dass interne und externe Benutzer Ihrer Domäne in der Lage sind, mithilfe von Instant Messaging, Webkonferenzen und Audio/Video zusammenzuarbeiten?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Remotebenutzer](external-access-policies/configure-policies-to-control-remote-user-access.md)Zugriffs und [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Möchten Sie zulassen, dass anonyme Benutzer teilnehmen und zu Konferenzen eingeladen werden, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen wie im Thema [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) und [Erstellen von Konferenzrichtlinien](../conferencing/create-policies.md)detailliert.

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbunddomänen Kontakten gestatten?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](external-access-policies/configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und [Verwalten von SIP-Verbunddomänen für Ihre Organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die automatische Erkennung von SIP-Föderationen aktivieren?**

Konfigurieren Sie die Einstellungen wie im Thema [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern](access-edge/enable-or-disable-discovery-of-federation-partners.md)beschrieben.

**Wenn Sie die Kommunikation mit SIP-Föderationsdomänen aktiviert haben, möchten Sie das Senden einer Verzichtserklärung an Föderations Kontakte aktivieren, die Sie darüber informiert, dass Sie die Archivierung verwenden und die Kommunikation archiviert werden kann?**

Konfigurieren Sie die Einstellungen, wie im Thema [Aktivieren oder Deaktivieren des Sendens von Archivierungs verzichten an verbundene Partner in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbund Anbietern gestatten, die die Kommunikation mit öffentlichen Anbietern ermöglichen?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer](external-access-policies/configure-policies-to-control-public-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)sowie unter [erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) .


**Möchten Sie zulassen, dass Benutzer mit SIP-Verbund Anbietern kommunizieren, die gehostete Anbieter mit Microsoft Office 365 und Skype for Business Online sind?**

Konfigurieren Sie die Einstellungen wie in den Themen unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) sowie unter [erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)beschrieben.

**Ist Ihre Bereitstellung in einer geteilten (auch als Hybrid bezeichneten) Domäne konfiguriert, in der einige Benutzer über Ihren Homeserver in einer lokalen Bereitstellung verfügen und andere Benutzer mit einem Homeserver in einer Online Umgebung konfiguriert sind?**

Konfigurieren Sie die Einstellungen, wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](external-access-policies/configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)sowie unter [erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)beschrieben.


Sie können Einstellungen für den externen Benutzer Zugriff konfigurieren, einschließlich aller Richtlinien, die Sie zum Steuern des Zugriffs auf externe Benutzer verwenden möchten, auch wenn Sie den Zugriff auf externe Benutzer für Ihre Organisation nicht aktiviert haben. Die Richtlinien und anderen Einstellungen, die Sie konfigurieren, sind jedoch nur wirksam, wenn der Zugriff auf externe Benutzer für Ihre Organisation aktiviert ist. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der Zugriff auf externe Benutzer deaktiviert ist oder wenn keine Richtlinien für den externen Benutzer Zugriff für die Unterstützung konfiguriert sind.

Ihre Edge-Bereitstellung authentifiziert die Typen externer Benutzer (mit Ausnahme von anonymen Benutzern, die von der Konferenz-ID authentifiziert werden, und einem Kennwort, das an den anonymen Teilnehmer gesendet wird, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und Steuerelemente Access basiert auf der Konfiguration Ihrer Edge-Unterstützung. Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren und Einstellungen konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die standardmäßige globale Richtlinie für den Zugriff durch externe Benutzer sowie Website-und Benutzerrichtlinien, die Sie erstellen und konfigurieren können, um einen oder mehrere Typen von externen Benutzer Zugriff für bestimmte Websites oder Benutzer zu ermöglichen.

