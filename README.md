import { Contract, GlobalState } from "@algorandfoundation/tealscript";

export class Treasure extends Contract {
  // A global state variable to store the treasure
  treasure = GlobalState<string>({ key: "treasure", initialValue: "" });

  // Function to hide (set) the treasure
  hideTreasure(secret: string): string {
    this.treasure.value = secret;
    return "Treasure hidden!";
  }

  // Function to find (get) the treasure
  findTreasure(): string {
    return this.treasure.value;
  }
}
