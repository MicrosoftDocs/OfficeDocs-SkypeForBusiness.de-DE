---
title: Migrieren des Vermittlungsservers
TOCTitle: Migrieren des Vermittlungsservers
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205173(v=OCS.15)
ms:contentKeyID: 49295116
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren des Vermittlungsservers

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Ihr Vermittlungsserver wird bei der Ausführung des Zusammenführungs-Assistenten mit der Pilottopologie von Lync Server 2013 zusammengeführt. Sie konfigurieren den Vermittlungsserver von Lync Server 2013 jedoch erst nach der Migration aller Benutzer, da ein Office Communications Server 2007 R2-Pool nicht mit einem Vermittlungsserver von Lync Server 2013 kommunizieren kann. Während der parallelen Migration kommuniziert der Lync Server 2013-Pool mit dem Vermittlungsserver von Office Communications Server 2007 R2.

Wenn Sie den Vermittlungsserver von Lync Server 2013 konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2-Gateways aktualisieren oder ersetzen. Der Vermittlungsserver von Lync Server 2013 wird nicht von Office Communications Server 2007 R2-Gateways unterstützt. Sie müssen Gateways bereitstellen, die für Lync Server 2013 zertifiziert sind, und sie dem Vermittlungsserver von Lync Server 2013 zuordnen. Vor der vollständigen Deaktivierung Ihrer Bereitstellung von Office Communications Server 2007 R2 muss dieser Schritt ausgeführt werden.

In den Themen in diesem Abschnitt werden Konfigurationsaufgaben beschrieben, die nach der Migration des Vermittlungsservers von Lync Server 2013 ausgeführt werden müssen. Der Übergang des verbundenen Vermittlungsservers in einen eigenständigen Vermittlungsserver ist eine optionale Aufgabe.

  - [Konfigurieren des Vermittlungsservers](configure-mediation-server.md)

  - [Ändern der VoIP-Routen für die Verwendung des neuen Lync Server 2013-Vermittlungsservers](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Wechseln von einem verbundenen Vermittlungsserver zu einem eigenständigen Übermittlungsserver (optional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

