# π₯ fe-sprint-github-actions-practice
* κΈ°μ‘΄ μκ³ λΌμ€νμ΄μΈ  μλ² μ°μ΅ μ½λλ₯Ό μ¬μ©νμ¬ κΉνλΈ μ‘μμ μ°μ΅ν΄λ³Έλ€.
[κΉν μ‘μ κ³΅μλ¬Έμ](https://docs.github.com/en/actions)
* .yaml(.yml) λ¬Έλ²μ μ λ¦¬νλ€.

<br/><br/>

## π‘ κΉν μ‘μμ λνμ¬
* Github actionsλ₯Ό λ¬΄λ£λ‘ μ¬μ©νκΈ° μν΄μ  λ ν¬μ§ν λ¦¬κ° public μ΄μ΄μΌ νλ€.
* λΉκ³΅κ° λ ν¬μ§ν λ¦¬μ κ²½μ° Github Actionsκ° μλν  λμ μ©λκ³Ό μκ°μ΄ μ νλμ΄μλ€.
* GitHub Actionsλ Githubκ° κ³΅μμ μΌλ‘ μ κ³΅νλ λΉλ, νμ€νΈ λ° λ°°ν¬ νμ΄νλΌμΈμ μλνν  μ μλ CI/CD νλ«νΌμ΄λ€.
* λ ν¬μ§ν λ¦¬μμ Pull Request λ push κ°μ μ΄λ²€νΈλ₯Ό νΈλ¦¬κ±°λ‘ GitHub μμ μν¬νλ‘(Workflow)λ₯Ό κ΅¬μ±ν  μ μλ€.
* μν¬νλ‘λ νλ μ΄μμ μμμ΄ μ€νλλ μλν νλ‘μΈμ€λ‘, κ° μμμ μμ²΄ κ°μ λ¨Έμ  λλ μ»¨νμ΄λ λ΄λΆμμ μ€νλλ€.
* μν¬νλ‘λ .yml (νΉμ .yaml ) νμΌμ μν΄ κ΅¬μ±λλ©°, νμ€νΈ, λ°°ν¬ λ± κΈ°λ₯μ λ°λΌ μ¬λ¬κ°μ μν¬νλ‘λ λ§λ€ μ μλ€.
* μμ±λ μν¬νλ‘λ .github/workflows λλ ν λ¦¬ μ΄νμ μμΉνλ€.

<br/><br/>

## π€ YAMLμ΄λ
* **Yet Another Markup Language**μ μ½μλ‘, jsonκ°μ΄ μ¬λμ΄ μ½μ μ μλ λ°μ΄ν° μ§λ ¬ν μΈμ΄λ₯Ό λ§νλ€.
*  .yaml νΉμ .yml νμ₯μλ₯Ό κ°μ§λ€.
* μ½κ³  μ΄ν΄νκΈ° μ¬μ°λ©° λ€λ₯Έ νλ‘κ·Έλλ° μΈμ΄μ ν¨κΌ μ¬μ©νκΈ° μ’λ€. 
* μ€μ  νμΌ(configure file λ±)μ μ¬μ©νκΈ°μ μ’λ€.
* μ μ°μ±κ³Ό μ κ·Όμ± λλΆμ κΉν μ‘μκ³Ό κ°μ μλν νλ‘μΈμ€λ₯Ό μμ±νλ λ°μλ μ¬μ©λλ€.(ex. μΏ λ²λ€ν°μ€)

<br/><br/>

## π₯ JSON vs YAML
* μλλ Github actions μ€μ μ μν΄ μμ±λ YAML νμΌ μμ μ΄λ€.
```yaml
name: Bare Minimum Requirements
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Bare Minimum Requirements
        uses: actions/setup-node@v1
        with:
          node-version: '16'
      - run: npm install
      - run: npm test
```
* μλλ MDNμ JSON νμΌμ΄λ€.
```json
{
  "squadName": "Super hero squad",
  "homeTown": "Metro City",
  "formed": 2016,
  "secretBase": "Super tower",
  "active": true,
  "members": [
    {
      "name": "Molecule Man",
      "age": 29,
      "secretIdentity": "Dan Jukes",
      "powers": [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    }
  ]
}
```
**πκ³΅ν΅μ **
* JSON νμΌκ³Ό YAML νμΌμ key-value ννλ‘ μμ±λ νμΌμ΄λ€.
* JSON νμΌκ³Ό YAML νμΌμ κ³μΈ΅ κ΅¬μ‘°λ₯Ό κ°μ§λ€.

<br/>

**πμ°¨μ΄μ **
* YAML νμΌμ "" (ν°λ°μ΄ν, double quotation marks) μμ΄ λ¬Έμμ΄ μμ±μ΄ κ°λ₯ν΄, μ€μ μ μν μ€νμ΄λ νλ‘νΌν° κ° λ±μ΄ JSON νμΌμ λΉν΄ ν λμ λ€μ΄μ¨λ€.
* SON νμΌμ²λΌ {} ννλ‘ κ°μΈμ€ νμλ μκΈ° λλ¬Έμ μ€μ½νμ μλ°(μλͺ» μ°λ©΄ μΌμΌμ΄ μ΄λκ° μ²μμ΄κ³  λμΈμ§ μ°ΎμμΌ νλ λ±)μμ λ²μ΄λ  μλ μλ€.
*  YAML νμΌμ JSON νμΌκ³Ό λ€λ₯΄κ² μ£Όμμ μμ±ν  μ μλ€. π?
* YAMLμ JSONμ μμ νΈν κ²©μ΄λ―λ‘, κΈ°μ‘΄ jsonλ¬Έμλ₯Ό κ·Έλλ‘ yamlνμΌλ‘ μ¬μ©νκ±°λ μνλ λΆλΆλ§ μλ³Ό μ μλ€. (λ°λλ‘ yamlμ jsonμΌλ‘ λ³νν΄ μ¬μ©ν  μλ μλ€)

<br/><br/>

## π₯ YAML λ¬Έλ²

#### β¦οΈ λ¬Έμμμ, λ, μ£Όμ
```yaml
#μ΄λ° μμΌλ‘ μμ '#'μ μ μ΄ μ£Όμμ μμ±

--- #λ¬Έμ μμ (optional)

#μ΄ μ¬μ΄μ λ΄μ© (---μ ...μ¬μ΄)

... #λ¬Έμ λ (optional)
```
<br/>

#### β¦οΈ λ€μ¬μ°κΈ°
λ€μ¬μ°κΈ°λ κΈ°λ³Έμ μΌλ‘ 2μΉΈ λλ 4μΉΈμ μ§μνλ, λ³΄ν΅ 2μΉΈμ© λ€μ¬μ°λ κ²μ μΆμ²νλ€. ν­ ν€κ° μλ μ€νμ΄μ€ ν€λ‘ λ€μ¬μ¨μΌ ν¨.
<br/> 

#### β¦οΈ κΈ°λ³Ένν  
```yaml
key: value
# μ΄λ°μμΌλ‘ μ κ³  π ':' λ€λ―μ λ¬΄μ‘°κ±΄!! κ³΅λ°± λ¬Έμκ° μμΌν¨
```
<br/>

#### β¦οΈ μλ£ν
* **int, string, boolean, λ¦¬μ€νΈ, λ§€ν**μ μ§μ
* μ¬κΈ°μ intμ string νμμ μ€μΉΌλΌ(Scalar)λΌκ³  νλ€.
* λ°°μ΄ νΉμ λ¦¬μ€νΈλ μνμ€(Sequence)λΌκ³  νλ€.
* λ§€νμλ κΈ°λ³Έ ννμΈ key-value μ λ° hash, dictionaryκ° ν¬ν¨λλ€.
```yaml
#int(μ«μ)
int_type: 1

#string(λ¬Έμμ΄)
string_type: "1" 

#blooean(μ°Έ/κ±°μ§)
boolean_true_type: true
boolean_false_type: false

#μ΄μΈμ yes, noλ‘ μμ±νκΈ°λ ν¨.
yaml_easy: yes
yaml_difficult: no

#λ¦¬μ€νΈ(λ°°μ΄ νν) '-'λ‘ νν.
person:
  name: Chungsub Kim
  job: Developer
  skills: 
    - docker
    - kubernetes
  # JSON νμμ "skill" : [docker, kubernetes]μ κ°μ.
```
<br/>

#### β¦οΈ κ°μ²΄
* κ°μ²΄ ννμ key μμ± ν **λ μΉΈμ λ€μ¬μ¨μ** key-value ννλ‘ μμ±μ ν΄μ£Όκ±°λ, keyλ₯Ό μμ± ν **μ€κ΄νΈ({})**λ‘ ν λ² λ¬Άκ³  key-value ννλ‘ μμ±νλ€.
```yaml
key: 
  key: value
  key: value

#λλ μ΄λ κ²λ μμ±νλ€. κ°λμ±μ μν΄ μ¬μ©νλ€.
key: {
  key: value,
  key: value
}
```
<br/>

#### β¦οΈ Text
* μ€λ°κΏ νν(|)κ³Ό μ€λ°κΏ λ¬΄μ νν(>)μ΄ μλ€.
```yaml
# |: μ€λ°κΏ νν
# JSON νμμ "comment_line_break": "Hello codestates.\nIm kimcoding.\n"κ³Ό λμΌ
comment_line_break: |
  Hello codestates.
  Im kimcoding.

# >: μ€λ°κΏ λ¬΄μ νν
# JSON νμμ "comment_single_line": "Hello world my first coding."μ λμΌ
comment_single_line: >
  Hello world
  my first coding.
```
<br/>
 
#### β¦οΈ λ¬Έμμ΄ λ°μ΄ν
* key-value μμμ valueμ :κ° λ€μ΄κ° κ²½μ°λ **λ°λμ λ°μ΄νκ° νμ**
```yaml
# β error λ¨
windows_drive: c:

# β­οΈ μ΄λ κ² μ¨μΌ ν¨
windows_drive: "c:"
windows_drive: 'c:'
```

<br/><br/>

## π λμ μ¬ν μλ¬ λ‘κ·Έ
<br/>

**λ ν¬μ§ν λ¦¬ settings > secrets > actions μμ μλ‘μ΄ secretμ μ§μ νλ€.**
μ΄ λΆλΆμμ settings > environments > new environments λ‘ νλ©΄ μλλ€.
<br/>

envrionmentλ νκ²½μ΄κ³ , κ·Έ μμ scretsλ₯Ό μ€μ ν  μ μλ€. actionsμλ `environment: [νκ²½μ΄λ¦]`μ΄λ° μμΌλ‘ μ€μ ν΄μ νλ κ³Όμ λ€μ΄ μλ€. [μ°Έμ‘°](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)

```yaml
name: Some task

on:
  push:
    branches:
      - main

jobs:
  prod-task:
    runs-on: ubuntu-latest
    environment: production
    steps:
      # uses production enviroment secrets over repository secrets
      - name: Run node build process
        run: "NODE_ENV=${{ env.NODE_ENV }} npm run build"
  dev-task:
    runs-on: ubuntu-latest
    environment: development
    steps:
      # uses development enviroment secrets over repository secrets
      - name: Run node build process
        run: "NODE_ENV=${{ env.NODE_ENV }} npm run build"
  task:
    runs-on: ubuntu-latest
    steps:
      # uses repository secrets as no environment is defined
      - name: Run node build process
        run: "NODE_ENV=${{ env.NODE_ENV }} npm run build"
```


π₯ [λ§ν¬](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)λ₯Ό μ°Έμ‘°νμ¬ μ΄λ°μμΌλ‘ νλκ² λ§λ€.
<br/>

**aws s3 cp λμ  aws s3 syncλ₯Ό μ΄λ€.**
* `cp`λ λͺ©μ μ§ ν΄λμ μ΄λ―Έ νμΌμ΄ μ‘΄λνλλΌλ λͺ¨λ  νμΌμ μΉ΄νΌνλ€.
* `cp`λ λͺ©μ μ§ ν΄λμμμ μ­μ λ₯Ό μ§μνμ§ μλλ€. μμ€ ν΄λμμ νμΌμ μ­μ νλλΌλ s3μμ  μ­μ λμ§ μλλ€.
* `cp`λ --deleteμ ν¨κ» μΈ μ μλ€.[λ§ν¬](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/sync.html)μ delete μ΅μ μμ.
* `sync`λ μλ‘­κ±°λ μλ°μ΄νΈ λ νμΌλ§ μμ€ ν΄λμμ κ°μ§ν΄μ λͺ©μ μ§ s3ν΄λμ μ?κ²¨μ€λ€. νμΌμ λ³΅μ¬ν΄μ λ?μ΄μ°κΈ° μ μ λͺ©μ μ§ ν΄λλΆν° λ³΄λ©΄μ μ€λ³΅λλ κ²μ΄ μλμ§ μ²΄ν¬νλ€.
* `sync`μ ν¨κ» `--delete` νλκ·Έλ₯Ό μ°λ©΄ μμ€ν΄λμ μ­μ λ νμΌμ λͺ©μ μ§ ν΄λμμλ μ­μ ν  μ μλλ‘ ν΄μ€λ€. `--delete`κ° μμ€μ μλ νμΌμ΄ λͺ©μ μ§ s3μ μλ€λ©΄ μ§μΈ μ μλλ‘ μ§μνλ€. 
* syncλ νμΌμ μ¬μ΄μ¦μ κ°μ₯ μ΅κ·Όμ νΈμ§λ νμ μ€ν¬νλ₯Ό μ²΄ν¬νμ¬ μλ°μ΄νΈκ° νμνμ§ νλ¨νλ€. νμΌ λ΄μ©μ λΉκ΅νμ§ μλλ€. 
* μ¦ `cp`λ μ μ²΄ νμΌμ, `sync`λ μλ‘­κ±°λ μλ°μ΄νΈ λ ν΄λλ§ μλ‘λ νλ€.
* `sync`λ μμ€ ν΄λμ λͺ©μ μ§ ν΄λμ μ±ν¬λ₯Ό λμΌνκ² λ§μΆκ³  μ μ§νκ³ μ ν  λ μ¬μ©νλ€. μλ₯Όλ€μ΄μ, μ μ μΈ μΉμ¬μ΄νΈ ν΄λ κ΄λ¦¬κ°μ κ²½μ°μ μ’λ€.
* `cp`λ `sync`λ³΄λ€ λ λ¨μνκ³  μ±λ₯μ΄ μ’μ μμμ΄λ€. νμΌμ΄ μ κ±°λ λλ ν λ¦¬κ°μ μ±ν¬λ₯Ό λ§μΆλ©΄μ μμν΄μΌ νλ μμμ΄ μλλΌλ©΄ `cp`λ₯Ό μ΄λ€.
* [μ°Έκ³ λ§ν¬1](https://www.learnaws.org/2022/03/01/aws-s3-cp-sync/) [μ°Έκ³ λ§ν¬2](https://docs.aws.amazon.com/ko_kr/cli/latest/userguide/cli-services-s3-commands.html)
