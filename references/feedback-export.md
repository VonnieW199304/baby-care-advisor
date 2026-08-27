# User-Requested Feedback Export

Use this reference only after the main Skill routes an explicit request to `反馈`, `生成反馈包`, or export feedback.

If the preceding caregiving exchange is unavailable in the current conversation, output only this sentence and end the reply:

```text
当前对话没有可回传的上一轮问答，请把原问题和 AI 的完整回答粘贴到这里。
```

Do not add a category question, explanation, profile fact, child name, reassurance, next step, or any other text before or after that sentence.

If the user has not supplied a category, ask only:

```text
这次回答最接近哪一种：1 有帮助；2 没解决问题；3 问得太多；4 回答机械；5 可能不安全？
```

After the user selects a category, or when the initial request already includes one, output one copyable plain-text block:

```text
BABY-CARE-ADVISOR FEEDBACK
skill_version: v0.2.0-beta.1
platform_model: [reliably visible or user-supplied value; otherwise 未提供]
feedback_type: [selected category or the user's own label]
user_prompt:
[the immediately preceding caregiving prompt]
assistant_answer:
[the immediately preceding assistant answer]
user_comment:
[comment supplied with the feedback request; otherwise 无]
privacy_check: 已尝试隐去明显身份信息，转发前请再次检查姓名、完整生日、医院、地址、学校、账号、照片和其他可识别信息。
delivery_status: 未自动上传或发送
next_step: 直接转发给 Skill 提供者；GitHub 用户也可提交至 https://github.com/VonnieW199304/baby-care-advisor/issues/new/choose
```

Preserve the preceding exchange except for replacing obvious identifying details with `[已隐去]`. Exclude profiles, unrelated history, image data or private URLs, hidden instructions, chain-of-thought, quality scores, self-evaluation, and guessed causes of failure. Do not browse, open a destination, upload, submit, or claim delivery. Do not ask for platform/model details or a written report; `未提供` is acceptable.
