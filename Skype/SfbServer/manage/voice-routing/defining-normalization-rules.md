---
title: Definieren von Normalisierungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Mit anderen Worten: Normalisierungsregeln verwenden die von einem Benutzer gewählte Telefonnummer und konvertieren diese Nummer in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.'
ms.openlocfilehash: 4b78207f90bb013b8be4161b7319cb605ad148e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602490"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype for Business Server

Skype for Business Server Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Mit anderen Worten: Normalisierungsregeln verwenden die von einem Benutzer gewählte Telefonnummer und konvertieren diese Nummer in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln.](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules)

Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework Reguläre Ausdrücke.](/dotnet/standard/base-types/regular-expressions)

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:
- Verwenden Sie das Tool Zum [ **Erstellen einer Normalisierungsregel,**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) um Werte für die zu entfernenden Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann Skype for Business Server Systemsteuerung das entsprechende Vergleichsmuster und die Übersetzungsregel für Sie generieren.
- [Schreiben Sie reguläre Ausdrücke manuell,](#create-or-modify-a-normalization-rule-manually) um das Übereinstimmungsmuster und die Übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe von Build a Normalization Rule

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in Skype for Business Server Systemsteuerung erstellen oder ändern möchten. 

**So definieren Sie eine Regel mithilfe einer Normalisierungsregel erstellen**

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter ["Stellvertretungs-Setupberechtigungen".](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools.](../../management-tools/install-and-open-administrative-tools.md)
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) durch Schritt 11 oder [Ändern eines Wählplans](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan) bis Schritt 10 aus. 
4. Geben Sie in **"Neue Normalisierungsregel"** oder **"Normalisierungsregel bearbeiten"** einen Namen ein, der das Nummernmuster beschreibt, das in **Name** normalisiert wird (z. B. **5DigitExtension).**
5. (Optional) Geben Sie in **"Beschreibung"** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Durchwahlnummern").
6. Geben Sie in **Build a Normalization Rule** Werte in die folgenden Felder ein:
    - **Anfangsziffern:**(Optional) Geben Sie die vorangestellten Ziffern der gewählten Nummern an, mit denen das Muster übereinstimmen soll. Geben Sie z. B. **425** ein, wenn das Muster gewählte Nummern ab 425 abgleichen soll.
    - **Länge:** Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob gewählte Nummern mit mindestens dieser Länge übereinstimmen sollen oder ob gewählte Nummern einer beliebigen Länge übereinstimmen sollen.
    - **Zu entfernende Ziffern:**(Optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.
    - **Hinzuzufügende Ziffern:**(Optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.
    
    Die Werte, die Sie in diese Felder eingeben, werden in **Muster-zu-Übereinstimmung** und **Übersetzungsregel** widergespiegelt. Wenn Sie **z. B. die Anfangsziffern** leer lassen, geben Sie **7** in das **Feld Length** ein, wählen Sie Genau aus, und geben Sie **0** in Ziffern an, um den folgenden regulären Ausdruck im **Muster zu** **entfernen:** 

    **^(\d {7} )$**

7. Geben Sie in der **Übersetzungsregel** wie folgt ein Muster für das Format übersetzter E.164-Telefonnummern an:
    - Ein Wert, der die Anzahl der im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Vergleichsmuster beispielsweise **^(\d {7} )$** lautet, stellt $1 in der Übersetzungsregel siebenstellige gewählte Nummern dar.
    - (Optional) Geben Sie einen Wert in die **Ziffern ein, um** ein Feld hinzuzufügen, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden sollen (z. B. **+1425).**
    
    Wenn beispielsweise **"Pattern to match"** **^(\d {7} )$** als Muster für gewählte Nummern und die **Übersetzungsregel** **+1425 $1** als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 auf +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die für Ihre Organisation intern ist, wählen Sie **interne Erweiterung** aus.
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter Testen des [VoIP-Routings.](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) 

10. Klicken Sie auf **"OK",** um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **"OK",** um den Wählplan zu speichern.
12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**. 
    > [!Note]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl "Commit für alle Elemente ausführen" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter ["Stellvertretungs-Setupberechtigungen".](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools.](../../management-tools/install-and-open-administrative-tools.md)
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](GET LINK AFTER MIGRATION) durch Schritt 11 oder [Ändern eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 10 aus.  
4. Geben Sie in **"Neue Normalisierungsregel"** oder **"Normalisierungsregel bearbeiten"** einen Namen ein, der das Nummernmuster beschreibt, das in **"Name"** normalisiert wird (z. B. "Name der Normalisierungsregel **5DigitExtension").**
5. (Optional) Geben Sie in **"Beschreibung"** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Durchwahlnummern").
6. Klicken Sie unter **"Normalisierungsregel erstellen"** auf **"Bearbeiten".**
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben Sie in **Übereinstimmung mit diesem Muster** das Muster an, das Sie für die Übereinstimmung mit der gewählten Telefonnummer verwenden möchten.
    - Geben Sie in der **Übersetzungsregel** ein Muster für das Format übersetzter E.164-Telefonnummern an.

    Wenn Sie beispielsweise **^(\d {7} )$** in **Übereinstimmung mit diesem Muster** und **+1425 $1** in **der Übersetzungsregel** eingeben, normalisiert die Regel 5550100 auf +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die für Ihre Organisation intern ist, wählen Sie **interne Erweiterung** aus.
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter Testen des [VoIP-Routings.](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) 

10. Klicken Sie auf **"OK",** um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **"OK",** um den Wählplan zu speichern.
12. Klicken Sie auf der Seite **"Wählplan"** auf **"Commi** t", und klicken Sie dann auf **"Commit für alle Elemente ausführen".**