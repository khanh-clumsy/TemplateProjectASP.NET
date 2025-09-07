
---

## 🏗️ Kiến trúc tổng quan

- **Domain Layer (Nexus.Domain)**  
  Chứa các entity, value object, interface, và logic nghiệp vụ thuần (business rules).

- **Application Layer (Nexus.Application)**  
  Chứa các service, DTO, handler, validation. Toàn bộ logic nghiệp vụ gọi từ đây.  
  Sử dụng **CQRS** (Command & Query Responsibility Segregation) nếu cần.

- **Infrastructure Layer (Nexus.Infrastructure)**  
  Chứa code cụ thể để kết nối database (EF Core), gửi mail, logging, external services.  
  Implement các interface được định nghĩa ở **Domain** và **Application**.

- **Presentation Layer**  
  - **Nexus.WebApi**: Expose dữ liệu dưới dạng REST API cho client khác (mobile, SPA, v.v).  
  - **Nexus.WebApp**: ASP.NET Core MVC/WebApp dùng Razor Page hiển thị trực tiếp.

---

## ⚙️ Công nghệ sử dụng

- **.NET 8 / ASP.NET Core**
- **Entity Framework Core** (SQL Server / PostgreSQL)
- **Dependency Injection** tích hợp sẵn trong ASP.NET Core
- **FluentValidation** cho validation (nếu dùng)
- **Swagger** cho API documentation
- **AutoMapper** (nếu dùng để map DTO ↔ Entity)

---
