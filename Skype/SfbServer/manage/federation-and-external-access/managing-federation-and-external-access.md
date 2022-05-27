---
title: 'Lync Server 2013: Verwalten des Verbunds und des externen Zugriffs auf Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
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
description: Sie aktivieren und konfigurieren den Zugriff externer Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676217"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Verwalten von Partnerverbund und externem Zugriff auf Skype for Business Server

Die Bereitstellung eines Edgeservers oder Edgepools ist der erste Schritt zur Unterstützung externer Benutzer. Ausführliche Informationen zum Bereitstellen von Edgeservern finden [Sie unter Bereitstellen von Edgeservern in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Nach der Installation und Konfiguration Ihrer internen Bereitstellung von Skype for Business Server können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die über SIP-Konten in Ihrem Active Directory Domain Services (AD DS) verfügen. Die Zusammenarbeit kann das Senden und Empfangen von Chatnachrichten, die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch als "Besprechungen" bezeichnet) umfassen. Sie aktivieren und konfigurieren den Zugriff externer Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können. Externe Benutzer können Remotebenutzer Ihrer Bereitstellung, Verbundbenutzer (einschließlich unterstützter Benutzer von öffentlichen Chatdienstanbietern) und anonyme Teilnehmer an Konferenzen umfassen.

Wenn Ihre Bereitstellung einen Skype for Business Server Edgeserver oder einen Edgepool enthält, wird der Umfang möglicher Kommunikationstypen erheblich erweitert. Es gibt viele Optionen für den externen Benutzerzugriff, die Kommunikation mit Mitgliedern anderer SIP-Verbunddomänen und SIP-Verbundanbieter. Nach dem Einrichten des Edgeservers oder Edgepools aktivieren Sie die Zugriffstypen für externe Benutzer und konfigurieren Richtlinien, um den externen Zugriff zu steuern. In Skype for Business Server aktivieren und konfigurieren Sie den Zugriff und die Richtlinien für externe Benutzer mithilfe der Skype for Business Server Systemsteuerung, der [Skype for Business Server-Verwaltungsshell](../management-shell.md) oder beides.

> [!IMPORTANT]
> Beim Entwerfen der Konfiguration und der Richtlinien für externen Benutzerzugriff müssen Sie die Rangfolge der Richtlinien verstehen und wissen, wie Richtlinien angewendet werden. Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.

Standardmäßig unterstützen keine Richtlinien den Zugriff externer Benutzer (einschließlich Remotebenutzerzugriff und Verbundbenutzerzugriff), auch wenn Sie die Unterstützung für den externen Benutzerzugriff für Ihre Organisation bereits aktiviert haben. Um die Verwendung des externen Benutzerzugriffs zu steuern, müssen Sie eine oder mehrere Richtlinien konfigurieren. In den folgenden Richtlinien geben Sie den Typ des unterstützten externen Benutzerzugriffs an:

- **Globale Richtlinie**: Die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert. Um den Zugriff externer Benutzer auf globaler Ebene zu unterstützen, konfigurieren Sie die globale Richtlinie, um einen oder mehrere Arten des externen Benutzerzugriffs zu unterstützen. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt. Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.

- **Websiterichtlinie**: Sie können eine oder mehrere Websiterichtlinien erstellen und konfigurieren, um die Unterstützung für den externen Benutzerzugriff auf bestimmte Websites einzuschränken. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den bestimmten Standort, der von der Standortrichtlinie abgedeckt wird. Standardmäßig wird eine Websiterichtlinie auf alle Benutzer auf dieser Website angewendet, benutzerrichtlinien jedoch, um die Websiterichtlinieneinstellungen außer Kraft zu setzen.

- **Benutzerrichtlinie**: Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Remotebenutzerzugriff auf bestimmte Benutzer einzuschränken. Die Konfiguration in der Benutzerrichtlinie setzt die globale und die Standortrichtlinie außer Kraft, jedoch nur für die bestimmten Benutzer, denen die Richtlinie zugewiesen ist. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.

Anhand der folgenden Entscheidungspunkte können Sie ermitteln, welche Konfigurationseinstellungen und Richtlinien Sie erstellen oder bearbeiten müssen:

**Möchten Sie internen und externen Benutzern Ihrer Domänen die Zusammenarbeit per Chat, Webkonferenzen und Audio/Video erlauben?**

Konfigurieren Sie die Einstellungen wie in den Themen ["Konfigurieren von Richtlinien zum Steuern von Remotebenutzerzugriffen](external-access-policies/configure-policies-to-control-remote-user-access.md)" und ["Aktivieren oder Deaktivieren von Verbund- und öffentlichen Chatverbindungen](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)" beschrieben.

**Möchten Sie zulassen, dass anonyme Benutzer an Konferenzen teilnehmen können, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen wie im Thema ["Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) " und ["Erstellen von Konferenzrichtlinien"](../conferencing/create-policies.md) beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbunddomänen-Kontakten erlauben?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](external-access-policies/configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) und [Verwalten von SIP-Verbunddomänen für Ihre Organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).

**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die automatische Ermittlung des SIP-Partnerverbunds aktivieren?**

Konfigurieren Sie die Einstellungen wie im Thema ["Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern"](access-edge/enable-or-disable-discovery-of-federation-partners.md) beschrieben.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie das Senden eines Haftungsausschlusses an die Partnerverbundkontakte aktivieren, um sie über eine mögliche Archivierung der Kommunikation zu informieren?**

Konfigurieren Sie die Einstellungen wie im Thema ["Aktivieren oder Deaktivieren des Sendens eines Archivierungshaftungsausschlusses an Verbundpartner"](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbundanbietern ermöglichen, die die Kommunikation mit öffentlichen Anbietern ermöglichen?**

Konfigurieren Sie die Einstellungen gemäß den Themen [Konfigurieren von Richtlinien zum Steuern des öffentlichen Benutzerzugriffs](external-access-policies/configure-policies-to-control-public-user-access.md), [Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten öffentlicher SIP-Verbundanbieter](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbundanbietern ermöglichen, die gehostete Anbieter sind, die Microsoft 365 oder Office 365 und Skype for Business Online ausführen?**

Konfigurieren Sie die Einstellungen wie in den Themen ["Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) " beschrieben, und [erstellen oder bearbeiten Sie gehostete SIP-Verbundanbieter](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Ist Ihre Domäne als geteilte Domäne (auch als Hybridomäne bezeichnet) konfiguriert, in der einige Benutzer einen Homeserver in einer lokalen Bereitstellung haben und für andere Benutzer ein Homeserver in einer Onlineumgebung konfiguriert ist?**

Konfigurieren Sie die Einstellungen gemäß den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](external-access-policies/configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren der Verbund- und öffentlichen Chatkonnektivität](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

Sie können Einstellungen für den Zugriff externer Benutzer konfigurieren, auch wenn Sie den externen Benutzerzugriff für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien und anderen Einstellungen sind jedoch nur wirksam, wenn der externe Benutzerzugriff für Ihre Organisation aktiviert ist. Externe Benutzer können nicht mit Ihren Benutzern kommunizieren, wenn der Zugriff durch externe Benutzer deaktiviert ist oder wenn keine Richtlinien für den Zugriff durch externe Benutzer für die Unterstützung konfiguriert sind.

Ihre Edgebereitstellung authentifiziert die Typen externer Benutzer und steuert den Zugriff basierend auf der Konfiguration der Edgeunterstützung. Die Ausnahme von dieser Regel sind anonyme Benutzer, die durch die Konferenz-ID und einen Passkey authentifiziert werden, der an den anonymen Teilnehmer gesendet wird, wenn Sie die Konferenz erstellen und Teilnehmer einladen. Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Organisation miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die globale Standardrichtlinie, Standortrichtlinien und Benutzerrichtlinien, die Sie erstellen und konfigurieren können.
