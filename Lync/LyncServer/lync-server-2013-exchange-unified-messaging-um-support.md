---
title: 'Lync Server 2013: Unterstützung für Exchange Unified Messaging (UM)'
TOCTitle: Unterstützung für Exchange Unified Messaging (UM)
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398179(v=OCS.15)
ms:contentKeyID: 49293169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung für Exchange Unified Messaging (UM) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (UM), um Voicemessaging und E-Mail-Messaging in einer einzigen Messaginginfrastruktur zu kombinieren. In Exchange 2013 besteht Exchange UM aus dem Exchange UM-Dienst, der auf dem Postfachserver installiert und ausgeführt wird, und aus UM Call Router, der auf dem Clientzugriffsserver installiert und ausgeführt wird. Für Lync Server 2013-Enterprise-VoIP-Bereitstellungen kombiniert Exchange UM Voicemessaging und E-Mail-Messaging in einem einzigen Speicher, auf den von einem Telefon (also Outlook Voice Access) oder von einem Computer aus zugegriffen werden kann. Exchange UM und Lync Server 2013 werden gemeinsam eingesetzt, um Mailboxansagen, Outlook Voice Access und die Dienste der automatischen Telefonzentrale für Enterprise-VoIP-Benutzer bereitzustellen.

Zusätzlich zu der Unterstützung der Integration in lokale Bereitstellungen von Exchange UM unterstützt Lync Server 2013 auch die Integration mit gehosteten Exchange UM-Diensten. Dies ermöglicht Ihnen die Bereitstellung von Voicemessaging für Ihre Benutzer, wenn Sie einige oder alle Benutzer zu einem gehosteten Exchange-Dienstanbieter wie beispielsweise Microsoft Exchange Online migrieren.

Lync Server 2013 unterstützt die folgenden Versionen:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Microsoft Exchange Server 2007 mit Service Pack 1 (SP1) (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

Sie können Exchange UM mit Lync Server 2013 oder einer Lync Server 2013-Datenbank verbinden. Sie können Exchange UM und Lync Server 2013 in separaten Gesamtstrukturen installieren.


> [!NOTE]
> Bei Enterprise-VoIP-Bereitstellungen mit Integration einer Nebenstellenanlage ist Exchange UM möglicherweise nicht erforderlich, da Voicemail und die dazugehörigen Dienste den Benutzern ggf. über die Nebenstellenanlage bereitgestellt werden können. Wenn Sie die Nebenstellenanlage zu einem späteren Zeitpunkt aufgeben (z.&nbsp;B. bei der Bereitstellung von SIP-Trunking für PSTN-Festnetzkonnektivität), müssen Sie Exchange UM neu konfigurieren, um Benutzern, die bisher das Voicemailsystem der Nebenstellenanlage genutzt haben, Voicemailfunktionen zu bieten.



## In diesem Abschnitt

  - [Komponenten und Topologien für lokales Unified Messaging in Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Unterstützung für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

