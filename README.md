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





