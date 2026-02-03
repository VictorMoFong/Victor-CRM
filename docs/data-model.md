# 数据模型（建议版）

## 实体与关系
- **Customer**（客户）
- **ContactLog**（沟通记录）
- **PipelineStage**（阶段）
- **Contract**（合同）
- **Payment**（回款）
- **Channel**（渠道）
- **User**（员工/顾问）

## 字段示例
### Customer
- id, name, phone, email
- source_channel_id
- intent_country, intent_program
- priority, status, owner_user_id
- created_at, updated_at

### ContactLog
- id, customer_id, user_id
- channel_type (call/wechat/email/meeting)
- content_summary, next_follow_up_at
- sentiment, intent_score
- created_at

### PipelineStage
- id, name, order, is_closed

### Contract
- id, customer_id, signed_at, amount
- status, owner_user_id

### Payment
- id, contract_id, due_at, amount, paid_at

### Channel
- id, name, type, contact_person, status

### User
- id, name, role, team

## 关键关系
- Customer 1:N ContactLog
- Customer 1:1 Contract（可扩展为 1:N）
- Contract 1:N Payment
- Channel 1:N Customer
- User 1:N Customer
- User 1:N ContactLog

