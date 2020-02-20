---
title: Definieren von Übersetzungsregeln in Skype for Business Server
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
description: Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern normalisiert in das E. 164-Format weiter. Dies bedeutet, dass alle gewählten Zeichenfolgen im E. 164-Format zum Zweck der Durchführung von Reverse Number Lookup (können) normalisiert werden müssen, damit Sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Anrufer-ID-Präsentation zu bearbeiten.
ms.openlocfilehash: 49598c2ef6b1a145c206bece3e06068067b0a0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151205"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definieren von Übersetzungsregeln in Skype for Business Server

Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern normalisiert in das E. 164-Format weiter. Dies bedeutet, dass alle gewählten Zeichenfolgen im E. 164-Format zum Zweck der Durchführung von Reverse Number Lookup (können) normalisiert werden müssen, damit Sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Anrufer-ID-Präsentation zu bearbeiten.

Bei Skype for Business Server kann die Telefonnummer des angerufenen (d. h. die Telefonnummer genannt) aus dem E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (d. h. das zugeordnete Gateway, die private Zweigstelle Exchange (PBX) oder SIP trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.

## <a name="caller-id-presentation"></a>Darstellung der Anrufer-ID

Skype for Business Server bietet die Möglichkeit, auch die Telefonnummer des Anrufers (d. h. die Telefonnummer, die der Anrufer anruft) aus dem E. 164-Format in das lokale Wählformat zu übersetzen, das vom trunk-Peer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe "+44" am Beginn einer Wählzeichenfolge entfernt und durch "0144" ersetzt.

**So konfigurieren Sie die Anrufer-ID mithilfe der Skype for Business Server-Systemsteuerung**

1. Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter [Install and Open Administration Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Doppelklicken Sie auf der Seite Trunkkonfiguration auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.
5. So konfigurieren Sie die Rufnummernanzeige:
    - Klicken Sie auf **Auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie in **Übersetzungsregeln für Anrufernummern** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.
    - Wenn Sie eine neue Übersetzungsregel erstellen und dem Trunk zuordnen möchten, klicken Sie auf **Neu**. 
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.
    - Um eine vorhandene Übersetzungsregel zu kopieren, die als Ausgangspunkt für die Definition einer neuen Regel verwendet werden soll, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren**und dann auf **Einfügen**.
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

> [!Warning] 
> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

## <a name="called-id-presentation"></a>Aufgerufene ID-Präsentation

> [!Important]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine *Alternative* zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten. 

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:

- [Verwenden Sie das Tool zum Erstellen einer Übersetzungsregel](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die entsprechende Muster-und Übersetzungsregel für die Skype for Business Server-Systemsteuerung generieren.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-translation-rule-manually) , um das übereinstimmende Muster und die Übersetzungsregel zu definieren.

> [!Note]
> Informationen zum Schreiben von regulären Ausdrücken finden Sie unter [.NET Framework reguläre Ausdrücke](https://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Wertesatz in das Tool zum Erstellen einer Übersetzungsregel eingeben und die Skype for Business Server-Systemsteuerung zum Generieren der entsprechenden Übereinstimmungsmuster-und Übersetzungsregel für Sie aktivieren. 

**So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel**

1. Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter [Install and Open Administration Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Um mit der Definition einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Configure a trunk with Media Bypass](GET LINK AFTER MIGRATION)through Step 10 oder [Configure a trunk without Media Bypass](GET LINK AFTER MIGRATION) through Step 9 aus.
4. Geben Sie unter **Name** auf der Seite **neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. Optional Geben Sie unter **Beschreibung**eine Beschreibung für die Übersetzungsregel ein (beispielsweise **US International Dialing**für Ferngespräche).
6. Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds Werte in die folgenden Felder ein:
    - **Starting digits**: (optional) geben Sie die führenden Ziffern von Zahlen an, die mit dem Muster übereinstimmen sollen. Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E. 164-Format (die mit + beginnen) abzugleichen.
    - **Length**: Geben Sie die Anzahl der Stellen im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster Zahlen entsprechen soll, die diese Länge genau, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise **11** ein, und wählen Sie **mindestens** in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern abzugleichen.
    - **Zu entfernende Ziffern**: (optional) geben Sie die Anzahl der zu entfernenden Start Ziffern an. Geben Sie beispielsweise **1** ein, um den + vom Anfang der Zahl zu entfernen.
    - **Hinzuzufügende Ziffern**: (optional) geben Sie Ziffern an, die den übersetzten Zahlen vorangestellt werden sollen. Geben Sie beispielsweise " **011** " ein, wenn Sie möchten, dass die übersetzten Nummern beim Anwenden der Regel auf "011" vorangestellt werden.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Übereinstimmung** und **Übersetzungs** Regel wiedergegeben. Wenn Sie beispielsweise die obigen Beispielwerte angeben, lautet der resultierende reguläre Ausdruck im Feld **Muster in matc**h:
    
    **^\+(\d{9}\d +) $** 

    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Zahlen an. Dieses Muster besteht aus zwei Teilen:
    - Ein Wert (beispielsweise **$1**), der die Anzahl der Stellen im übereinstimmenden Muster darstellt.
    - Optional Ein Wert, den Sie voranstellen können, indem Sie ihn in das Feld **hinzuzufügende Ziffern** eingeben

    Mit den obigen Beispielwerten wird **011 $1** im **Übersetzungsregel** Feld angezeigt.
    
    Wenn diese Übersetzungsregel angewendet wird, wird + 441235551010 zu 011441235551010.
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
9. Klicken Sie auf der Seite **trunk-Konfiguratio**n auf **Commit**, und klicken Sie dann auf **Commit für alle**. 

> [!Note]
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Manuelles Erstellen oder Ändern einer Übersetzungsregel

Führen Sie diese Schritte aus, um eine Übersetzungsregel zu definieren, indem Sie einen regulären Ausdruck für das Vergleichsmuster und die Übersetzungsregel schreiben. 

**So definieren Sie eine Übersetzungsregel manuell**

1. Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter [Install and Open Administration Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Um mit der Definition einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Configure a trunk with Media Bypass](GET LINK AFTER MIGRATION)through Step 10 oder [Configure a trunk without Media Bypass](GET LINK AFTER MIGRATION) through Step 9 aus.
4. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. Optional Geben Sie in **Beschreibung**eine Beschreibung der Übersetzungsregel ein; Beispiel: **US International Dialing**(Ferngespräche).
6. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie Folgendes in das Feld Typ a **regulärer Ausdruck**ein:
    - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

    Wenn Sie beispielsweise ** ^ \+(\d{9}\d +) $** in **übereinstimmen mit diesem Muster** und **011 $1** in der **Übersetzungsregel**eingeben, übersetzt die Regel + 441235551010 in 011441235551010.
8. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
9. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

> [!Note] 
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 
