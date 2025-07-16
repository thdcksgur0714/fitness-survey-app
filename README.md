page1.js




import { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";
import ProgressBar from "../components/ProgressBar"; // 경로는 맞게 수정

const OPTIONS = [
  { label: "입문", desc: "운동초보" },
  { label: "초급", desc: "자세는 조금 알지만 무슨 운동을 해야 할지 몰라요" },
  { label: "중급", desc: "운동 자세를 잘 알고, 나만의 루틴이 있어요" },
  { label: "고급", desc: "운동을 직업으로 삼을 만큼의 지식이 있어요" },
  { label: "전문가", desc: "운동 선수급의 지식과 경험을 갖고 있어요" }
];

export default function Page1({ onNext }) {
  const [selected, setSelected] = useState(null);

  return (
    <View style={styles.container}>
      <ProgressBar step={1} />
      <Text style={styles.title}>운동 수준이 어떻게 되시나요?</Text>
      <Text style={styles.subtitle}>
        적절한 운동 추천이 필요해요! 외부에 공개되지 않아요
      </Text>
      <View style={{ marginTop: 26 }}>
        {OPTIONS.map((opt, idx) => (
          <TouchableOpacity
            key={idx}
            style={[styles.option, selected === idx && styles.optionSelected]}
            onPress={() => setSelected(idx)}
            activeOpacity={0.8}
          >
            <Text style={styles.label}>{opt.label}</Text>
            <Text style={styles.desc}>{opt.desc}</Text>
          </TouchableOpacity>
        ))}
      </View>
      <View style={styles.arrowRow}>
        <TouchableOpacity
          style={[
            styles.arrowBtn,
            !Number.isInteger(selected) && { opacity: 0.4 }
          ]}
          onPress={() => Number.isInteger(selected) && onNext(selected)}
          disabled={!Number.isInteger(selected)}
        >
          <Text style={styles.arrowText}>➔</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#F7F8FA", padding: 28 },
  title: { fontSize: 21, fontWeight: "bold", marginBottom: 12, marginTop: 20 },
  subtitle: { fontSize: 14, color: "#666" },
  option: {
    backgroundColor: "#c5d6ee",
    borderRadius: 22,
    paddingVertical: 18,
    paddingHorizontal: 20,
    marginBottom: 15,
  },
  optionSelected: {
    backgroundColor: "#91b5ec",
    borderWidth: 2,
    borderColor: "#275ec0"
  },
  label: { fontSize: 17, fontWeight: "bold", color: "#222" },
  desc: { fontSize: 14, color: "#34405a", marginTop: 5 },
  arrowRow: {
    flexDirection: "row",
    justifyContent: "flex-end",
    marginTop: 16,
  },
  arrowBtn: {
    backgroundColor: "#dde6f5",
    borderRadius: 50,
    padding: 9,
    alignItems: "center",
    justifyContent: "center",
    width: 44,
    height: 44,
  },
  arrowText: { fontSize: 23, color: "#34405a", fontWeight: "bold" },
});





page2.js
import { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";
import ProgressBar from "../components/ProgressBar";

const OPTIONS = [
  { label: "헬스장 기구", desc: "헬스장에 기구, 머신이 준비되어 있어요." },
  { label: "홈짐 기구", desc: "바벨, 덤벨, 머신들이 준비되어 있어요." },
  { label: "맨몸운동", desc: "기구 없이 몸 하나로 운동이 가능해요." },
  { label: "소도구 운동", desc: "덤벨, 케틀벨, 밴드 등의 운동들이 준비되어있어요." }
];

export default function Page2({ onNext, onBack }) {
  const [selected, setSelected] = useState(null);

  return (
    <View style={styles.container}>
      <ProgressBar step={2} />
      <Text style={styles.title}>어떤 기구를 사용할 수 있나요?</Text>
      <Text style={styles.subtitle}>
        기구 또는 장소에 따라 딱 맞게 추천해드려요
      </Text>
      <View style={{ marginTop: 26 }}>
        {OPTIONS.map((opt, idx) => (
          <TouchableOpacity
            key={idx}
            style={[styles.option, selected === idx && styles.optionSelected]}
            onPress={() => setSelected(idx)}
            activeOpacity={0.8}
          >
            <Text style={styles.label}>{opt.label}</Text>
            <Text style={styles.desc}>{opt.desc}</Text>
          </TouchableOpacity>
        ))}
      </View>
      <View style={styles.arrowRow}>
        <TouchableOpacity
          style={[styles.arrowBtn]}
          onPress={onBack}
        >
          <Text style={styles.arrowText}>←</Text>
        </TouchableOpacity>
        <TouchableOpacity
          style={[
            styles.arrowBtn,
            !Number.isInteger(selected) && { opacity: 0.4 }
          ]}
          onPress={() => Number.isInteger(selected) && onNext(selected)}
          disabled={!Number.isInteger(selected)}
        >
          <Text style={styles.arrowText}>➔</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#F7F8FA", padding: 28 },
  title: { fontSize: 21, fontWeight: "bold", marginBottom: 12, marginTop: 20 },
  subtitle: { fontSize: 14, color: "#666" },
  option: {
    backgroundColor: "#c5d6ee",
    borderRadius: 22,
    paddingVertical: 18,
    paddingHorizontal: 20,
    marginBottom: 15,
  },
  optionSelected: {
    backgroundColor: "#91b5ec",
    borderWidth: 2,
    borderColor: "#275ec0"
  },
  label: { fontSize: 17, fontWeight: "bold", color: "#222" },
  desc: { fontSize: 14, color: "#34405a", marginTop: 5 },
  arrowRow: {
    flexDirection: "row",
    justifyContent: "space-between",
    marginTop: 16,
  },
  arrowBtn: {
    backgroundColor: "#dde6f5",
    borderRadius: 50,
    padding: 9,
    alignItems: "center",
    justifyContent: "center",
    width: 44,
    height: 44,
  },
  arrowText: { fontSize: 23, color: "#34405a", fontWeight: "bold" },
});
loading Page2.js…]()





page3.js
import { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";
import ProgressBar from "../components/ProgressBar"; // 경로 맞게!

const OPTIONS = ["6회", "5회", "4회", "3회", "2회"];

export default function Page3({ onNext }) {
  const [selected, setSelected] = useState(null);

  return (
    <View style={styles.container}>
      <ProgressBar step={3}/>
      <Text style={styles.title}>일주일에 몇 번 운동하실 예정인가요?</Text>
      <Text style={styles.subtitle}>언제든지 변경할 수 있어요</Text>
      <View style={{ marginTop: 26 }}>
        {OPTIONS.map((opt, idx) => (
          <TouchableOpacity
            key={opt}
            style={[styles.option, selected === idx && styles.optionSelected]}
            onPress={() => setSelected(idx)}
            activeOpacity={0.8}
          >
            <Text style={styles.label}>{opt}</Text>
          </TouchableOpacity>
        ))}
      </View>
      <View style={styles.arrowRow}>
        <TouchableOpacity
          style={[
            styles.arrowBtn,
            !Number.isInteger(selected) && { opacity: 0.4 }
          ]}
          onPress={() => Number.isInteger(selected) && onNext(selected)}
          disabled={!Number.isInteger(selected)}
        >
          <Text style={styles.arrowText}>➔</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#F7F8FA", padding: 28 },
  title: { fontSize: 21, fontWeight: "bold", marginBottom: 12, marginTop: 20 },
  subtitle: { fontSize: 14, color: "#666" },
  option: {
    backgroundColor: "#c5d6ee",
    borderRadius: 22,
    paddingVertical: 18,
    paddingHorizontal: 20,
    marginBottom: 15,
  },
  optionSelected: {
    backgroundColor: "#91b5ec",
    borderWidth: 2,
    borderColor: "#275ec0"
  },
  label: { fontSize: 17, fontWeight: "bold", color: "#222" },
  arrowRow: {
    flexDirection: "row",
    justifyContent: "flex-end",
    marginTop: 16,
  },
  arrowBtn: {
    backgroundColor: "#dde6f5",
    borderRadius: 50,
    padding: 9,
    alignItems: "center",
    justifyContent: "center",
    width: 44,
    height: 44,
  },
  arrowText: { fontSize: 23, color: "#34405a", fontWeight: "bold" },
});







page4.js


import { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";
import ProgressBar from "../components/ProgressBar";

const OPTIONS = [
  { label: "추천 플랜" },
  { label: "스스로 만든 플랜" }
];

export default function Page4({ onNext, onBack }) {
  const [selected, setSelected] = useState(null);

  return (
    <View style={styles.container}>
      <ProgressBar step={4} />
      <Text style={styles.title}>어떤 플랫폼을 사용해서 운동을 시작할까요?</Text>
      <Text style={styles.subtitle}>언제든지 변경할 수 있어요</Text>
      <View style={{ marginTop: 26 }}>
        {OPTIONS.map((opt, idx) => (
          <TouchableOpacity
            key={idx}
            style={[styles.option, selected === idx && styles.optionSelected]}
            onPress={() => setSelected(idx)}
            activeOpacity={0.8}
          >
            <Text style={styles.label}>{opt.label}</Text>
          </TouchableOpacity>
        ))}
      </View>
      <View style={styles.arrowRow}>
        <TouchableOpacity
          style={[
            styles.arrowBtn,
            !Number.isInteger(selected) && { opacity: 0.4 }
          ]}
          onPress={() => Number.isInteger(selected) && onNext(selected)}
          disabled={!Number.isInteger(selected)}
        >
          <Text style={styles.arrowText}>➔</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#F7F8FA", padding: 28 },
  title: { fontSize: 21, fontWeight: "bold", marginBottom: 12, marginTop: 20 },
  subtitle: { fontSize: 14, color: "#666" },
  option: {
    backgroundColor: "#c5d6ee",
    borderRadius: 22,
    paddingVertical: 18,
    paddingHorizontal: 20,
    marginBottom: 15,
  },
  optionSelected: {
    backgroundColor: "#91b5ec",
    borderWidth: 2,
    borderColor: "#275ec0"
  },
  label: { fontSize: 17, fontWeight: "bold", color: "#222" },
  arrowRow: {
    flexDirection: "row",
    justifyContent: "flex-end",
    marginTop: 16,
  },
  arrowBtn: {
    backgroundColor: "#dde6f5",
    borderRadius: 50,
    padding: 9,
    alignItems: "center",
    justifyContent: "center",
    width: 44,
    height: 44,
  },
  arrowText: { fontSize: 23, color: "#34405a", fontWeight: "bold" },
});




page5.js

import { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";
import ProgressBar from "../components/ProgressBar"; // 경로 확인

const OPTIONS = [
  { label: "웨이트 입문", desc: "웨이트 트레이닝 시작하는데 기초를 다져요" },
  { label: "다이어트", desc: "체중을 감량하고 건강한 체형을 만들어요" },
  { label: "벌크업 (상급 노하우)", desc: "근육량과 더 큰 몸을 만들고 싶은 분들께 추천드려요" },
  { label: "린매스업", desc: "근육량은 늘리고 체지방은 내려 멋진 몸을 만들어요" },
  { label: "대회 준비", desc: "대회를 준비하시는 분들께 추천드려요" },
  { label: "건강한 습관 만들기", desc: "꾸준하게 실현할 수 있는 습관을 만들어요" }
];

export default function Page5({ onNext, onBack }) {
  const [selected, setSelected] = useState(null);

  return (
    <View style={styles.container}>
      <ProgressBar step={5} />
      <Text style={styles.title}>운동 시작 전,{"\n"}가장 중요한 목표는 무엇인가요?</Text>
      <View style={{ marginTop: 20 }}>
        {OPTIONS.map((opt, idx) => (
          <TouchableOpacity
            key={idx}
            style={[styles.option, selected === idx && styles.optionSelected]}
            onPress={() => setSelected(idx)}
            activeOpacity={0.8}
          >
            <Text style={styles.label}>{opt.label}</Text>
            <Text style={styles.desc}>{opt.desc}</Text>
          </TouchableOpacity>
        ))}
      </View>
      <View style={styles.arrowRow}>
        <TouchableOpacity
          style={[
            styles.arrowBtn,
            !Number.isInteger(selected) && { opacity: 0.4 }
          ]}
          onPress={() => Number.isInteger(selected) && onNext(selected)}
          disabled={!Number.isInteger(selected)}
        >
          <Text style={styles.arrowText}>➔</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#F7F8FA", padding: 28 },
  title: { fontSize: 21, fontWeight: "bold", marginBottom: 12, marginTop: 20 },
  option: {
    backgroundColor: "#c5d6ee",
    borderRadius: 22,
    paddingVertical: 16,
    paddingHorizontal: 20,
    marginBottom: 14,
  },
  optionSelected: {
    backgroundColor: "#91b5ec",
    borderWidth: 2,
    borderColor: "#275ec0"
  },
  label: { fontSize: 17, fontWeight: "bold", color: "#222" },
  desc: { fontSize: 14, color: "#34405a", marginTop: 5 },
  arrowRow: {
    flexDirection: "row",
    justifyContent: "flex-end",
    marginTop: 16,
  },
  arrowBtn: {
    backgroundColor: "#dde6f5",
    borderRadius: 50,
    padding: 9,
    alignItems: "center",
    justifyContent: "center",
    width: 44,
    height: 44,
  },
  arrowText: { fontSize: 23, color: "#34405a", fontWeight: "bold" },
});

 


progressbar.js

import { View } from "react-native";

export default function ProgressBar({ step }) {
  return (
    <View style={{ height: 8, marginBottom: 18, backgroundColor: "#e4e6ee", borderRadius: 6 }}>
      <View
        style={{
          backgroundColor: "#89aee6",
          height: 8,
          borderRadius: 6,
          width: `${(step / 10) * 100}%`,
        }}
      />
    </View>
  );
}








reset-project.js
#!/usr/bin/env node

/**
 * This script is used to reset the project to a blank state.
 * It deletes or moves the /app, /components, /hooks, /scripts, and /constants directories to /app-example based on user input and creates a new /app directory with an index.tsx and _layout.tsx file.
 * You can remove the `reset-project` script from package.json and safely delete this file after running it.
 */

const fs = require("fs");
const path = require("path");
const readline = require("readline");

const root = process.cwd();
const oldDirs = ["app", "components", "hooks", "constants", "scripts"];
const exampleDir = "app-example";
const newAppDir = "app";
const exampleDirPath = path.join(root, exampleDir);

const indexContent = `import { Text, View } from "react-native";

export default function Index() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: "center",
        alignItems: "center",
      }}
    >
      <Text>Edit app/index.tsx to edit this screen.</Text>
    </View>
  );
}
`;

const layoutContent = `import { Stack } from "expo-router";

export default function RootLayout() {
  return <Stack />;
}
`;

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

const moveDirectories = async (userInput) => {
  try {
    if (userInput === "y") {
      // Create the app-example directory
      await fs.promises.mkdir(exampleDirPath, { recursive: true });
      console.log(`📁 /${exampleDir} directory created.`);
    }

    // Move old directories to new app-example directory or delete them
    for (const dir of oldDirs) {
      const oldDirPath = path.join(root, dir);
      if (fs.existsSync(oldDirPath)) {
        if (userInput === "y") {
          const newDirPath = path.join(root, exampleDir, dir);
          await fs.promises.rename(oldDirPath, newDirPath);
          console.log(`➡️ /${dir} moved to /${exampleDir}/${dir}.`);
        } else {
          await fs.promises.rm(oldDirPath, { recursive: true, force: true });
          console.log(`❌ /${dir} deleted.`);
        }
      } else {
        console.log(`➡️ /${dir} does not exist, skipping.`);
      }
    }

    // Create new /app directory
    const newAppDirPath = path.join(root, newAppDir);
    await fs.promises.mkdir(newAppDirPath, { recursive: true });
    console.log("\n📁 New /app directory created.");

    // Create index.tsx
    const indexPath = path.join(newAppDirPath, "index.tsx");
    await fs.promises.writeFile(indexPath, indexContent);
    console.log("📄 app/index.tsx created.");

    // Create _layout.tsx
    const layoutPath = path.join(newAppDirPath, "_layout.tsx");
    await fs.promises.writeFile(layoutPath, layoutContent);
    console.log("📄 app/_layout.tsx created.");

    console.log("\n✅ Project reset complete. Next steps:");
    console.log(
      `1. Run \`npx expo start\` to start a development server.\n2. Edit app/index.tsx to edit the main screen.${
        userInput === "y"
          ? `\n3. Delete the /${exampleDir} directory when you're done referencing it.`
          : ""
      }`
    );
  } catch (error) {
    console.error(`❌ Error during script execution: ${error.message}`);
  }
};

rl.question(
  "Do you want to move existing files to /app-example instead of deleting them? (Y/n): ",
  (answer) => {
    const userInput = answer.trim().toLowerCase() || "y";
    if (userInput === "y" || userInput === "n") {
      moveDirectories(userInput).finally(() => rl.close());
    } else {
      console.log("❌ Invalid input. Please enter 'Y' or 'N'.");
      rl.close();
    }
  }
);






App.js

import React, { useState } from "react";
import Page1 from "./screens/Page1";
import Page2 from "./screens/Page2";
import Page3 from "./screens/Page3";
import Page4 from "./screens/Page4";
import Page5 from "./screens/Page5";

const LABELS = [
  ["입문", "초급", "중급", "고급", "전문가"],
  ["헬스장 기구", "홈짐 기구", "맨몸운동", "소도구 운동"],
  ["6회", "5회", "4회", "3회", "2회"],
  ["추천 플랜", "스스로 만든 플랜"],
  [
    "웨이트 입문", "다이어트", "벌크업 (상급 노하우)",
    "린매스업", "대회 준비", "건강한 습관 만들기"
  ]
];

export default function App() {
  const [step, setStep] = useState(0);
  const [answers, setAnswers] = useState([]);

  const handleNext = (selectedIdx) => {
    setAnswers((prev) => {
      // 과거 수정 가능하게 만들려면 prev.slice(0,step) 등
      const copied = [...prev];
      copied[step] = selectedIdx;
      return copied;
    });
    setStep((prev) => prev + 1);
  };

  if (step === 0)
    return <Page1 onNext={handleNext} />;
  if (step === 1)
    return <Page2 onNext={handleNext} onBack={() => setStep(0)} />;
  if (step === 2)
    return <Page3 onNext={handleNext} onBack={() => setStep(1)} />;
  if (step === 3)
    return <Page4 onNext={handleNext} onBack={() => setStep(2)} />;
  if (step === 4)
    return <Page5 onNext={handleNext} onBack={() => setStep(3)} />;

  // 결과 화면
  return (
    <React.Fragment>
      <Result answers={answers} />
    </React.Fragment>
  );
}

function Result({ answers }) {
  return (
    <div style={{
      background: "#f7f8fa", minHeight: "100vh", padding: 32, fontFamily: "sans-serif"
    }}>
      <h2>설문 응답 결과</h2>
      <ol style={{ fontSize: 18 }}>
        {answers.map((v, i) => (
          <li key={i}>{LABELS[i][v]}</li>
        ))}
      </ol>
    </div>
  );
}

