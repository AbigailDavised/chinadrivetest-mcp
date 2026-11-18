---
name: chinadrivetest
description: "Query all 2,545 bilingual China Subject 1 driving exam questions, grade mock exams with SM-2 intervals, check MPS Order No. 172 bilateral license swaps, locate 9 airport temporary permit counters, and map foreign licenses to Chinese C1/C2 classes via ChinaDriveTest's stateless MCP server."
homepage: https://chinadrivetest.com
version: 1.0.0
license: MIT
compatibility: "Works with Hermes Agent, Claude Code, Cursor, Windsurf, and any MCP client supporting Streamable HTTP."
metadata:
  homepage: "https://chinadrivetest.com"
  mcp_endpoint: "https://chinadrivetest.com/api/mcp"
  version: "1.0.0"
  hermes:
    category: travel
    tags: [china-driving-license, subject-1-test, temporary-driving-permit, dmv-china, road-signs]
---

# ChinaDriveTest — Stateless China Driving License & Subject 1 MCP Skill

Connect any MCP-compatible AI agent to ChinaDriveTest's public read-only Streamable HTTP server at `https://chinadrivetest.com/api/mcp`. Zero sign-in or API keys required.

## Endpoint Configuration

```json
{
  "mcpServers": {
    "chinadrivetest": {
      "type": "streamable-http",
      "url": "https://chinadrivetest.com/api/mcp"
    }
  }
}
```

## Direct JSON-RPC 2.0 Verification

```bash
curl -s -X POST https://chinadrivetest.com/api/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"query_airport_temporary_permit_counter","arguments":{"airportQuery":"PVG","includeArrivalSteps":true}}}'
```

## Tools Inventory (8 Read-Only Tools)

- `search_subject1_exam_questions`: Filter 2,545 bilingual China driving theory exam items across 9 chapters by keyword, difficulty, and error rate.
- `grade_mock_exam_and_sm2_schedule`: Grade submissions against the 90/100 statutory threshold with SuperMemo-2 spacing intervals or generate weighted drills.
- `evaluate_foreign_license_conversion_and_mutual_swap`: Evaluate MPS Order No. 172 zero-exam mutual swaps (FR/BE/AE/RS/HK/MO), tourist permits, and age-70+ rules.
- `query_airport_temporary_permit_counter`: Locate 15-minute ¥10 RMB temporary permit counters across 9 Chinese international airports.
- `query_city_dmv_conversion_guide`: Street addresses, metro exits, 12123 booking, and taxi cards for Shanghai, Beijing, Shenzhen, Guangzhou, and Chengdu DMVs.
- `generate_dmv_license_translation_and_class_map`: Deterministic 3-character DMV Chinese name synthesis and foreign-to-C1/C2/E-D class translation.
- `lookup_chinese_road_signs_and_demerit_points`: 25 GB5768 road signs, 8 police hand gestures, and Order No. 172 demerit brackets (12/9/6/3/1 pts).
- `plan_china_self_drive_route_and_rental`: Duku Highway G217, Sichuan G318, and Hainan Ring Road logistics plus foreign-card car rental agencies.
