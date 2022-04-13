## Interfaces

- Defines a structure of object.
- Focuses on abstract, external properties
- Interfaces + abstract classes strong code reuse with TypeScript

```javascript
const oldCivic = {
  name: "civic",
  year: 2000,
  broken: true,
};

const printVehicleDetails = (vehicle: {
  name: string,
  year: number,
  broken: boolean,
}): void => {
  console.log(`Name: ${vehicle.name}`);
  console.log(`Year: ${vehicle.year}`);
  console.log(`Name: ${vehicle.broken}`);
};
```

```javascript
interface Vehicle {
  name: string;
  year: number;
  broken: boolean;
}

const oldCivic = {
  name: "civic",
  year: 2000,
  broken: true,
};

const printVehicleDetails = (vehicle: Vehicle): void => {
  console.log(`Name: ${vehicle.name}`);
  console.log(`Year: ${vehicle.year}`);
  console.log(`Broken: ${vehicle.broken}`);
};

printVehicleDetails(oldCivic);
```

```javascript
interface Vehicle {
  name: string;
  year: number;
  broken: boolean;
  summary(): string;
}

const oldCivic = {
  name: "civic",
  year: 2000,
  broken: true,
  summary() {
    return `Name: ${this.name}
           Year: ${this.year}
           Broken: ${this.broken}
          `;
  },
};

const printVehicleDetails = (vehicle: Vehicle): void => {
  console.log(vehicle.summary());
};

printVehicleDetails(oldCivic);
```

```javascript
interface Reportable {
  summary(): string;
}

const oldCivic = {
  name: "civic",
  year: 2000,
  broken: true,
  summary() {
    return `Name: ${this.name}
           Year: ${this.year}
           Broken: ${this.broken}
          `;
  },
};

const printVehicleDetails = (report: Reportable): void => {
  console.log(report.summary());
};

printVehicleDetails(oldCivic);
```

```javascript
interface Reportable {
  summary(): string;
}


const drink = {
    sugarLevel:30,
    carbonated:true
    type:"cola",
    summary(){
        return `Sugar level: ${this.sugarLevel}
           Carbonated: ${this.carbonated}
           Type: ${this.type}
          `;
    }
}


const oldCivic = {
  name: "civic",
  year: 2000,
  broken: true,
  summary() {
    return `Name: ${this.name}
           Year: ${this.year}
           Broken: ${this.broken}
          `;
  },
};

const printSummary = (report: Reportable): void => {
  console.log(report.summary());
};


printSummary(drink);

printSummary(oldCivic);

```

- Interface use for function gate-keeping
- Objects/Classes can decide to implement a given interface to work with a function
